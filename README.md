# Counterfeit_drug_detection
Youtube link



Counterfeit drugs pose a severe threat to public health, leading to ineffective treatments, increased resistance to genuine medications, and significant economic losses. These fake medications undermine trust in healthcare systems and can result in life-threatening consequences for patients.
Our project focused on detecting counterfeit drugs using a confidence score. The user needs to enter information for smiles, inchi, hydrogen bond donors, and logp, and based on this information, the model then predicts the drug with the confidence score. Based on how high or low the confidence score is, users can then make an informed decision about the authenticity of the drug. 

To achieve this, we started by installing the required packages and libraries. 
Then, we loaded our dataset and went through the preprocessing processes to prepare the data for training.
Our focus was to identify counterfeit anti-malaria drugs, so we had to filter the dataset to ensure that the drugs it contains are only antimalaria drugs before continuing with the other processes. 
We achieved this by creating a vocabulary for the malaria drugs. We matched the drugs to see if they contained any malaria-related words in the vocabulary and filtered the data frame. 

Then, we loaded the llama-2-7b-chat-hf model (chat model) directly in 4-bit precision using the NF4 type and trained it for one epoch on the mlabonne/guanaco-llama2-1k (1,000 samples).
We then loaded the configurations for QLoRA and regular training parameters and passed everything to the SFTTrainer.
Then, the fine-tuning began. 
We needed parameter-efficient fine-tuning (PEFT) techniques like LoRA or QLoRA. To drastically reduce the VRAM usage, we fine-tuned the model in 4-bit precision, using QLoRA.
The text generation pipeline was used to ask questions like “What is a large language model?” To format the input to match the Llama 2 prompt template.

To store our new Llama-2-7b-chat-finetune model, the base model was reloaded in FP16 precision, and the left library was used to merge everything.
We then reloaded the tokenizer since our weights were merged and pushed everything to Huggining Face Hub to save the model.








