# Livekit

A project integrating speech-to-text (STT), large language models (LLM), text-to-speech (TTS), and various AI models including `gpt-4o-mini`, `gemini-2.5-flash`, `gpt-4o-realtime`, and `gemini-2.5-flash-preview-native-audio-dialog` with LiveKit for real-time audio and conversational applications.

## Description

This repository provides scripts to interact with LiveKit and multiple AI services for building real-time conversational agents with STT, LLM, and TTS capabilities.

## Prerequisites

- Python 3.8+
- Git
- A LiveKit account with API keys
- API keys for OpenAI, Google, Deepgram, and Cartesia

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/reuban-zacker/livekit.git
   cd livekit
   ```

2. **Set up a virtual environment**:
   ```bash
   python -m venv .venv
   ```
   - On Windows:
     ```bash
     .\.venv\Scripts\Activate.ps1
     ```
   - On macOS/Linux:
     ```bash
     source .venv/bin/activate
     ```

3. **Install dependencies**:
   ```bash
   pip install livekit-agents[deepgram,openai,google,cartesia,silero,turn-detector]~=1.2.2
   pip install livekit-plugins-noise-cancellation~=0.2.5
   pip install torch
   pip install python-dotenv
   ```

4. **Create and configure the `.env` file**:
   In the `livekit` directory, create a `.env` file with the following content (google and gemini api keys are same):
   ```
   OPENAI_API_KEY=your_openai_api_key
   GEMINI_API_KEY=your_gemini_api_key
   GOOGLE_API_KEY=your_google_api_key
   LIVEKIT_API_KEY=your_livekit_api_key
   LIVEKIT_API_SECRET=your_livekit_api_secret
   LIVEKIT_URL=your_livekit_url
   CARTESIA_API_KEY=your_cartesia_api_key
   DEEPGRAM_API_KEY=your_deepgram_api_key
   ```
   Replace `your_..._api_key` with your actual API keys.

## Usage

Run the following scripts to download required files and start the console for each supported model:

- **GPT-4o-mini**:
  ```bash
  python gpt.py download-files
  python gpt.py console
  ```

- **Gemini-2.5-flash**:
  ```bash
  python gemini.py download-files
  python gemini.py console
  ```

- **GPT-4o-realtime**:
  ```bash
  python gptrealtime.py download-files
  python gptrealtime.py console
  ```

- **Gemini-2.5-flash-preview-native-audio-dialog**:
  ```bash
  python gemininative.py download-files
  python gemininative.py console
  ```

## Verify Installed Packages

To check the installed versions of the dependencies, run:
```bash
pip show livekit-agents livekit-plugins-google livekit-plugins-silero livekit-plugins-noise-cancellation torch
```

## Folder Structure

- `.venv/`: Virtual environment
- `.env`: Environment variables for API keys
- `gpt.py`: Script for GPT-4o-mini integration
- `gemini.py`: Script for Gemini-2.5-flash integration
- `gptrealtime.py`: Script for GPT-4o-realtime integration
- `gemininative.py`: Script for Gemini-2.5-flash-preview-native-audio-dialog integration
- `README.md`: Project documentation (this file)

## Contributing

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m "Add feature"`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a Pull Request on GitHub.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For issues or questions, open an issue on the [GitHub repository](https://github.com/reuban-zacker/livekit).
