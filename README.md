# Egyptian Arabic Speech AI
**ASR Benchmarking & Long-Form Speech Recognition Pipeline**

An end-to-end project focused on evaluating speech recognition models for Egyptian Arabic and building a long-form transcription pipeline.

<img width="1868" height="808" alt="image" src="https://github.com/user-attachments/assets/1fed89ed-7f3a-428a-8f1c-d43b7940e67f" />



## Tech Stack

**Python · LangChain · Hugging Face · Whisper · Jais-ASR · Silero VAD · Gradio · FFmpeg · jiwer**

## ASR Benchmark Results

Evaluated 9 ASR models on **60 Egyptian Arabic audio clips** from the `severo/Egyptian-ASR-MGB-3` dataset.

| Model                             | WER ↓  | Norm. WER ↓ | Norm. CER ↓ | RTF ↓ | 
| --------------------------------- | ------ | ----------- | ----------- | ----- |
| Whisper Small                     | 65.30% | 59.50%      | 25.00%      | 0.058 |
| Whisper Large-v3                  | 50.10% | 36.30%      | 15.90%      | 0.156 | 
| Whisper Large-v3 + Prompt         | 50.20% | 35.60%      | 15.50%      | 0.169 | 
| Whisper Large-v3 (Baseline Rerun) | 51.32% | 39.98%      | 22.75%      | 0.216 | 
| QwenCleo-ASR                      | 50.94% | 33.85%      | 18.79%      | 0.248 | 
| Whisper-v3-turbo Egyptian CS      | 55.36% | 42.65%      | 21.40%      | 0.060 |
| EgypTalk-ASR-v2                   | 54.59% | 27.75%      | 15.27%      | 0.009 | 
| Whisper-v3 Arabic Dialectal v2    | 48.29% | 34.51%      | 18.57%      | 0.236 | 
| Jais-ASR                          | 38.76% | 28.55%      | 15.74%      | 0.181 | 

**Key findings**
- Jais-ASR achieved the lowest raw WER at **38.76%**.
- EgypTalk-ASR-v2 achieved the lowest normalized WER and CER.
- EgypTalk-ASR-v2 recorded the lowest RTF in this benchmark.
- All six models processed the 60-clip evaluation set.

## What I Built

### 1. ASR Benchmarking Framework
- Evaluated multiple speech recognition models on the same dataset.
- Measured WER, normalized WER, CER, normalized CER, and real-time factor (RTF).
- Tracked transcription errors, loops, dropped clips, and truncations.

### 2. Long-Form Transcription Pipeline
- Audio preprocessing and standardization using FFmpeg.
- Voice Activity Detection using Silero VAD.
- Intelligent audio chunking for long recordings.
- Jais-ASR transcription with chunk splitting and retry handling.
- Transcript reconstruction into a complete output.

### 3. LLM-Powered Post-Processing
- LangChain-based transcript correction for obvious transcription errors.
- Automatic transcript summarization.

### 4. Gradio Interface
- Interactive interface for uploading audio and running transcription.
- Structured transcript outputs in TXT, JSON, and SRT formats.

## Getting Started

Both notebooks are designed to run in **Google Colab**.

### 1. Open the notebooks

Choose the notebook you want to run:

- `Egyptian_Arabic_ASR_Benchmark.ipynb` — compare ASR model performance.
- `Egyptian_Arabic_Speech_Recognition_Pipeline.ipynb` — run the complete transcription pipeline.

Upload the notebook to Google Colab or open it directly from the repository.

### 2. Configure the runtime

1. In Colab, open **Runtime → Change runtime type**.
2. Select a GPU accelerator if available.
3. Save the runtime settings.
4. Make sure the notebook has internet access to download the required models and dependencies.

### 3. Install dependencies

Run the notebook's setup and installation cells to install the required Python packages and prepare the environment.

### 4. Run the notebook

Execute the cells **from top to bottom**, allowing each cell to finish before moving to the next one.

- **Benchmark notebook:** Loads the evaluation dataset, runs the selected ASR models, and calculates the evaluation metrics.
- **Transcription notebook:** Initializes the pipeline components and prepares the Gradio interface.

### 5. Test the transcription pipeline

1. Launch the Gradio interface using the notebook.
2. Upload an audio recording.
3. Run the transcription process.
4. Review the generated transcript and summary.
5. Export the results in TXT, JSON, or SRT format.

## Notebooks

| Notebook | Description |
|---|---|
| `Egyptian_Arabic_ASR_Benchmark.ipynb` | Model evaluation and benchmarking |
| `Egyptian_Arabic_Speech_Recognition_Pipeline.ipynb` | Long-form transcription pipeline |

---


