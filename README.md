# Counterfeit Drug Detection

## Overview

Counterfeit drugs pose a severe threat to public health, leading to ineffective treatments, increased resistance to genuine medications, and significant economic losses. These fake medications undermine trust in healthcare systems and can result in life-threatening consequences for patients.

Our project focuses on detecting counterfeit drugs using a confidence score. Users need to enter information such as SMILES, InChI, hydrogen bond donors (HBD), and LogP. Based on this information, the model predicts the drug with a confidence score. Users can then make informed decisions about the authenticity of the drug based on the confidence score.

## Dataset

- [Link to Dataset](https://drive.google.com/file/d/1EARQOE5VLyioLl63Axk1aAgRgN6C-07b/view?usp=sharing)

## App

- [Link to the App](https://colab.research.google.com/drive/1RBw-F2QP3NzZ3tVmJwKKJxNe5EL3AMDs?usp=sharing#scrollTo=4VP-KcQDQ6po)

## How It Works

1. **Installation**: Install the required packages and libraries.
2. **Data Loading**: Load and preprocess the dataset for training.
3. **Data Filtering**: Filter the dataset to include only anti-malaria drugs.
4. **Model Training**:
   - Create a vocabulary for malaria drugs.
   - Match and filter the drugs based on the vocabulary.
   - created input and output columns based on following llama2 prompt templates
   - Load the Llama-2-7b-chat-hf model in 4-bit precision using NF4 type.
   - Train the model for five epochs.
   - Use parameter-efficient fine-tuning techniques like LoRA or QLoRA.
   - Fine-tune the model in 4-bit precision with QLoRA to reduce VRAM usage.
   - Use the text generation pipeline to format the input and ask questions.

5. **Model Storage**:
   - Reload the base model in FP16 precision.
   - Merge everything using the left library.
   - Reload the tokenizer and pushed everything to Hugging Face Hub.

## Usage

In the final project app (linked above), you can:
- Enter SMILES, InChI, HBD, and LogP values.
- See the model's prediction and confidence score.
- Make an informed decision about the authenticity of the drug.

Due to high RAM requirements, the app is deployed on Google Colab rather than other platforms like Streamlit.

## YouTube Link

*(Add your YouTube link here)*

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
