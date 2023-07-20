# Notbot-Chatbot-for-Internship-tasks

from flask import Flask, request
from twilio.twiml.messaging_response import MessagingResponse
app = Flask(_name_)
def incoming():
    incoming_message=request.values.get('Body','').lower()
    resp=MessagingResponse()
    message=resp.message()
    if 'hi' in incoming_message:
        message.body('Hi! are you here to apply for the intership {YES} OR {NO}')
    elif 'YES' in incoming_message:
        message.body('Please enter your name')
    elif 'NO' in incoming_message:
        message.body('OK, Fine.')
    elif 'Name' in incoming_message:
        message.body('Please enter your e-mail id')
    elif 'email-id' in incoming_message:
        message.body('Please select how many years of experience you have with python/js/Automation Development')
        message.body('Short List 1,2,3,4,5 .years')
    elif 'experience' in incoming_message:
        message.body('Thanks for connecting we will get back to you shortly')
    return str(resp)
if _name_ == '_main_':
    app.run()
