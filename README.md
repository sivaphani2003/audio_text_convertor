# YouTube Audio to Text and Text-to-Speech Pipeline

This project provides a pipeline that downloads audio from a YouTube video, transcribes it to text using the Deepgram API, and converts the transcribed text back into speech using the Eleven Labs API.

## Features

- **Download YouTube Video**: Extracts the audio from a YouTube video and saves it as an MP3 file.
- **Transcribe Audio to Text**: Uses the Deepgram API to convert the downloaded audio into text.
- **Text to Speech**: Uses the Eleven Labs API to convert the transcribed text back into an audio file (MP3).

## Technologies Used

- [yt-dlp](https://github.com/yt-dlp/yt-dlp): To download YouTube videos as audio.
- [Deepgram API](https://deepgram.com/): To transcribe audio to text.
- [Eleven Labs API](https://beta.elevenlabs.io/): For text-to-speech conversion.

## Prerequisites

1. **Python 3.x** installed on your machine.
2. **API Keys**:
   - Deepgram API Key: Obtain from [Deepgram](https://developers.deepgram.com/).
   - Eleven Labs API Key: Obtain from [Eleven Labs](https://beta.elevenlabs.io/).

## Installation

1. Clone this repository:
    ```bash
    git clone https://github.com/sivaphani2003/audio_text_convertor.git
    cd audio_text_convertor
    ```

2. Install the required dependencies:
    ```bash
    pip install yt_dlp moviepy requests
    ```

3. Add your API keys to the code:
   - Update `eleven_labs_api_key` and `deepgram_api_key` with your own keys in the script.

## Usage

1. **Download and Transcribe YouTube Audio**:
   Update the `url` variable with the YouTube video link you want to download and transcribe.

2. **Run the Script**:
   Execute the script with the following command:
    ```bash
    python your_script_name.py
    ```

3. **Output**:
   - The YouTube audio is saved as an MP3 file.
   - The transcription is printed in the console.
   - The final text-to-speech output is saved as an MP3 file.

## Example

```python
eleven_labs_api_key = 'your_eleven_labs_api_key'
deepgram_api_key = 'your_deepgram_api_key'

# Example YouTube video
url = "https://www.youtube.com/watch?v=xyz"  
output_filename = "my_audio_file"

# Download YouTube audio
download_video(url, output_filename)

# Convert audio to text
audio_file_path = 'my_audio_file.mp3'
transcript = audio_to_text(audio_file_path, deepgram_api_key)

# Convert text to speech
if transcript:
    text_to_speech(transcript, eleven_labs_api_key, 'voice_id', 'output_audio')
```

## Notes

- The current implementation uses YouTube video URLs and processes videos of reasonable length. If the transcript is too long, consider using a shorter video.
- Make sure you have the required API quotas and permissions for using Deepgram and Eleven Labs APIs.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

