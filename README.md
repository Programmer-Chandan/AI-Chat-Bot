# AI-Chat-Bot
It is code for creating a simple AI Chat box with python using streamlit and google -generativeai library  

import streamlit as st
import google.generativeai as genai

key="API key of your AI"
genai.configure(api_key=key)

model= genai.GenerativeModel(model_name="gemini-1.5-flash")
chat= model.start_chat()


st.title("😍😎AI chatbot🤖")
input = st.text_area("enter your prompt here!!")

if st.button("Ask!"):
    if input.strip():
        reply = chat.send_message(input)
        st.subheader("AI Response:")
        st.write(reply.text)
    else:
        st.warning("Please enter a prompt!!")


