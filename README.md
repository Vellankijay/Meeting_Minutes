# AI Meeting Minutes Generator 📝

An end-to-end AI assistant that converts meeting audio recordings into professional meeting minutes. It uses **OpenAI Whisper API** for speech-to-text transcription and **LLaMA-based language models** to summarize and structure the minutes in Markdown, optimized for low VRAM environments using 4-bit quantization.

---

## 🚀 Features
- 🎙️ **Audio Transcription** using Whisper API.
- 🧠 **Meeting Minutes Generation** using LLaMA-based models.
- 📋 Structured output: Summary, Discussion Points, Takeaways, and Action Items with Owners.
- 🌐 Interactive Gradio interface for easy uploads and results.
- ⚡ Supports low VRAM machines through 4-bit quantization and CPU offloading.

---

## 🏗️ Project Structure
├── app.py # Main application logic (transcription + summarization)
├── interface.py # Gradio interface setup
├── requirements.txt # Python dependencies
└── README.md # Project documentation


---

## 📝 How It Works
1. Upload a `.mp3` audio file.
2. The audio is transcribed using **OpenAI Whisper**.
3. The transcribed text is processed by a **LLaMA model** to generate clean, structured meeting minutes.
4. Outputs Markdown-formatted minutes including:
   - Summary (Attendees, Date, Location)
   - Discussion Points
   - Takeaways
   - Action Items (with Owners)

---

## 🖥️ Example Usage (Python)
```python
assistant = MeetingAssistant()

audio_file = "meeting_audio.mp3"
for partial_output in assistant.process_meeting(audio_file, progress=print):
    print(partial_output, end="")
```

## Technologies Used  
OpenAI Whisper API  
Hugging Face Transformers  
LLaMA models with 4-bit quantization for efficient inference  
Gradio for frontend UI  

##📊 Applications  
Automated meeting documentation.  
AI-powered corporate reporting.  
Productivity tools for teams.  
AI-driven note-taking assistants.  
