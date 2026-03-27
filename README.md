# vityarthi---AI-ML-project
Make better captions in seconds — a Flask web app that uses Google's Gemini API to create short, mood-aware Instagram captions from a brief post description.

# Caption Crafter AI

A small Flask web app that generates short Instagram captions using Google's Gemini API. You enter a description of your post and choose a mood, and the app generates a short caption for you.

👉 **Live Demo:**  
https://caption-crafter-ai-1.onrender.com/

## Note on Render Free Tier
This project is hosted on Render's free tier. Free instances go to sleep after 15 minutes of inactivity. When the service has been idle, the first request may take 40–60 seconds to start the app again. After that, the app works normally.

## 📱 Demo Preview  


<img width="1722" height="958" alt="image" src="https://github.com/user-attachments/assets/b2d50e50-ec3a-44d2-8393-fc68e640f725" />


## Features

* 🚀 Features

* Clean and modern UI
* One-click caption generation
* Uses the Gemini gemini-2.0-flash REST endpoint
* Multiple moods like funny, romantic, casual, inspirational and more.
* Handles API rate limits safely
* Works locally and on cloud platforms
* Deployment-ready for Render, Railway, ngrok, and Heroku

## How it works

1. You submit a description and select the mood.
2. The backend sends a short prompt to the Gemini API.
3. The app calls:
   `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent`
4. The model returns a caption.  
5. The app displays one clean line of text.

## Installation

Install the required packages:

```
pip install flask requests python-dotenv
```

## Environment variables

Create a `.env` file (or set these in your system):

```
GEMINI_API_KEY=your_api_key_here
MOCK_FALLBACK=1   # optional; enables mock captions when no key is present
FLASK_ENV=development
```

If you don’t set `GEMINI_API_KEY`, the app will still run. With fallback enabled, it returns mock captions.

## Running the app

Start the server:

```
python app.py
```

Open the app in your browser:

```
http://localhost:5000
```

## Project structure

## 📁 Project structure  
```
/
│ app.py
│ requirements.txt
│ runtime.txt
│ Procfile
│ README.md
│ DEPLOYMENT.md
│ .gitignore
│
└── templates/
    └── index.html
```
## Notes

* Don’t commit your API key to GitHub.
* Debug logs can reveal parts of prompts and responses. Keep debug mode off in production.
* You can adjust `REQUEST_DELAY` in the code if you run into rate-limit errors.

## 🌍 Deployment  
A full guide on how to deploy this project is included in `DEPLOYMENT.md`.

## Future improvements

* Separate Gemini client module
* Stronger rate limiting or caching
* Optional authentication before generating captions
