# Phishing Detection via LoRA-Adapted DistilBERT (Milestone 3)
**By:** Hashim Abdulla

## Project Overview
This project classifies emails as Benign (0) or Phishing (1) to prevent credential harvesting. It compares a Base System (untrained DistilBERT classification head) against an Adapted System (DistilBERT fine-tuned using LoRA) to demonstrate the efficacy of parameter-efficient fine-tuning for semantic text classification.

## Environment & Setup Instructions
1. Make sure Python 3.10+ is installed.
2. Install the required deep learning and PEFT dependencies:
   `pip install torch transformers peft scikit-learn matplotlib seaborn pandas`
3. Place `extended_corpus.jsonl` in the `code/` directory alongside the notebook.

## Hardware Assumptions
This pipeline is configured to leverage CUDA hardware acceleration. It was tested locally on an NVIDIA RTX 3050 GPU. Training takes approximately under 2 minutes on this hardware.

## How to Run & Reproduce Results
1. Open `code/final_system.ipynb` in Jupyter or VS Code.
2. Click "Run All". 
3. The notebook will automatically:
   - Tokenize the dataset using `DistilBertTokenizer`.
   - Evaluate the Base System (zero-shot).
   - Inject LoRA adapters (Rank=8, Alpha=16) into the attention modules.
   - Train the Adapted System.
   - Evaluate the Adapted System and generate a comparative metrics table.
4. All plots (`base_cm.png`, `lora_cm.png`) and logs are saved automatically to the `../results/` folder relative to the code directory.

## Demo
Please see `demo_link.txt` for the URL to the 5-minute video presentation and a breakdown of the demo steps.
