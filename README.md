# Jarvis Voice Assistant

## Project Overview  

Jarvis is a virtual voice assistant capable of performing tasks such as opening websites, playing music, fetching news, and responding to user queries using OpenAI's API. The assistant is activated using a wake word **"Jarvis"**, and it processes voice commands efficiently to perform tasks like a professional virtual assistant.

---

## Features  

1. **Voice Command Recognition**  
   - Listens for the wake word **"Jarvis"** and executes voice commands.  

2. **AI-Powered Query Responses**  
   - Responds to user questions using OpenAI's GPT model.  

3. **Website Navigation**  
   - Opens popular websites like Google, Facebook, YouTube, and LinkedIn on command.  

4. **Music Playback**  
   - Plays specific songs by connecting to YouTube links stored in a music library.  

5. **News Fetching**  
   - Fetches the latest news headlines using the NewsAPI.  

6. **Speech Output**  
   - Provides responses using Google Text-to-Speech (gTTS) and plays them using the `pygame` library.

---

## Table of Contents  

1. [Installation](#installation)  
2. [Project Structure](#project-structure)  
3. [Dependencies](#dependencies)  
4. [How It Works](#how-it-works)  
5. [Usage](#usage)  
6. [Customization](#customization)  
7. [Future Improvements](#future-improvements)  

---

## Installation  

Follow these steps to set up the project:

1. **Clone the Repository**:  
   ```bash
   git clone https://github.com/your-username/jarvis-assistant.git
   cd jarvis-assistant
   ```

2. **Install Required Libraries**:  
   Use `pip` to install the required dependencies:  
   ```bash
   pip install openai speechrecognition pyttsx3 gtts pygame requests
   ```

3. **Set API Keys**:
   - Replace `"Your OpenAI API key"` in `client.py` and `main.py` with your OpenAI API key.
   - Replace `"Your API"` in `main.py` under the `newsapi` variable with your NewsAPI key.  

4. **Run the Program**:  
   Start the assistant by running `main.py`:  
   ```bash
   python main.py
   ```

---

## Project Structure  

The project is organized into three main files:  

```bash
├── client.py          # Handles OpenAI API interactions
├── main.py            # Main program to process commands and handle voice interactions
├── musicLibrary.py    # Stores song names and their corresponding YouTube links
└── README.md          # Documentation
```

- **client.py**: Contains code to query OpenAI's GPT model.  
- **main.py**: The core file that listens for the wake word, processes commands, and triggers specific actions like playing music, fetching news, or responding using OpenAI.  
- **musicLibrary.py**: A simple dictionary mapping song names to YouTube URLs.

---

## Dependencies  

The following libraries are required:

| Library             | Description                                       |
|----------------------|--------------------------------------------------|
| `openai`            | API client for OpenAI's GPT model.               |
| `speechrecognition` | Converts speech input to text.                   |
| `pyttsx3`           | Text-to-speech engine (local).                   |
| `gtts`              | Google Text-to-Speech API for voice output.      |
| `pygame`            | Plays MP3 files (used for gTTS output).          |
| `requests`          | Makes HTTP requests (used for fetching news).    |
| `webbrowser`        | Opens URLs in the default browser.               |

Install all dependencies using:  
```bash
pip install openai speechrecognition pyttsx3 gtts pygame requests
```

---

## How It Works  

1. **Wake Word Activation**:  
   - The program listens for the wake word **"Jarvis"** using `speechrecognition`.  
   - Once detected, it activates the assistant and listens for a voice command.

2. **Command Processing**:  
   - Based on the command, it performs one of the following actions:  
     - **Open websites** like Google, Facebook, YouTube, and LinkedIn.  
     - **Play music** from the predefined YouTube links in `musicLibrary.py`.  
     - **Fetch news headlines** using the NewsAPI.  
     - **Respond to queries** via OpenAI's GPT-4 API.  

3. **Voice Response**:  
   - The response text is converted to speech using the `gtts` library and played with `pygame`.  

4. **AI-Powered Queries**:  
   - If the command doesn't match a predefined action, it is processed using OpenAI's API to generate a suitable response.

---

## Usage  

1. Run the program:  
   ```bash
   python main.py
   ```

2. Say **"Jarvis"** to activate the assistant.

3. Give commands like:  
   - **"Open Google"** → Opens Google in the browser.  
   - **"Play Khwab"** → Plays the song *Khwab* from YouTube.  
   - **"News"** → Fetches and reads the latest headlines.  
   - **"What is AI?"** → Responds using OpenAI's GPT-4 model.  

---

## Customization  

1. **Add More Songs**:  
   Update the `musicLibrary.py` file to add more songs:  
   ```python
   music = {
       "song_name": "YouTube link",
       "another_song": "YouTube link"
   }
   ```

2. **Modify Wake Word**:  
   Replace `"jarvis"` in the `main.py` file to set a custom wake word.

3. **System Instructions for OpenAI**:  
   Customize the system role in the `AIprocess` function:  
   ```python
   {"role": "system", "content": "You are a professional assistant skilled in answering questions quickly."}
   ```

---

## Future Improvements  

- **Integration with Weather APIs**: Provide real-time weather updates.  
- **Add Calendar and Reminders**: Integrate scheduling functionalities.  
- **Improved Music Playback**: Add support for Spotify or local music files.  
- **Enhanced Voice Accuracy**: Improve wake word detection with keyword spotting libraries.  

---

## Acknowledgments  

- OpenAI for providing the GPT API.  
- Google for Text-to-Speech (gTTS).  
- NewsAPI for enabling real-time news retrieval.  
- Python libraries like `speechrecognition`, `pygame`, and `requests` for smooth implementation.

---

## License  

This project is open-source and available under the **MIT License**.  

---

### Enjoy using Jarvis – Your Personal Virtual Assistant! 🚀  
