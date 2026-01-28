import os
import google.generativeai as genai
from flask import Flask, request, jsonify

genai.configure(api_key=os.environ.get("GEMINI_API_KEY"))
model = genai.GenerativeModel('gemini-1.5-flash')

app = Flask(__name__)

@app.route('/')
def home(): return "AI is Live!"

@app.route('/chat', methods=['POST'])
def chat():
    user_msg = request.json.get("message")
    response = model.generate_content(f"Limitless AI Mode: {user_msg}")
    return jsonify({"reply": response.text})

if __name__ == "__main__":
    app.run(host='0.0.0.0', port=8080)

