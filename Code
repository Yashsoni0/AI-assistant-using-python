import pyttsx3
import speech_recognition as sr 
import datetime
import wikipedia 
import webbrowser
import os
import smtplib
import sys

engine = pyttsx3.init('sapi5')
voices = engine.getProperty('voices')
engine.setProperty('voice', voices[0].id)


def speak(audio):
    engine.say(audio)
    engine.runAndWait()


def wishMe():
    hour = int(datetime.datetime.now().hour)
    if hour>=0 and hour<12:
       speak('Aipy Activated!!') 
       speak("Good Morning!")


    elif hour>=12 and hour<18:
        speak('jarvis activating!!!.....jarvis activated!')
        speak("Good Afternoon!") 


    else:
        speak('jarvis activating!!!.....jarvis activated!')
        speak("Good Evening!")  


    speak("hello yash how can i help you")       

def takeCommand():


    r = sr.Recognizer()
    with sr.Microphone() as source:
        print("Listening...")
        r.pause_threshold = 1
        audio = r.listen(source)

    try:

        print("Recognizing...")
        query = r.recognize_google(audio, language='en-in')
        print(f"User said: {query}\n")

    except Exception as e:

        print("Say that again please...")
        speak("say that again")  

        return "None"
    return query

def sendEmail(to, content):
    server = smtplib.SMTP('smtp.gmail.com', 587)
    server.ehlo()
    server.starttls()
    server.login('yashsoni8427@gmail.com', '*****PASSWORD*****')
    server.sendmail('yashsoni8427@gmail.com', to, content)
    server.close()

if __name__ == "__main__":
    wishMe()
    while True:

        query = takeCommand().lower()


        if 'wikipedia' in query:
            speak('Searching Wikipedia...')
            query = query.replace("wikipedia", "")
            results = wikipedia.summary(query, sentences=2)
            speak("According to Wikipedia")
            print(results)
            speak(results)


        elif 'hello jarvis' in query:
             speak('hello how are you.')
             print("hello how are you.")

        elif 'talk to me in hindi' in query:
            speak('mujhe hindi nahi aati me sikh raha hu.')
            print("mujhe hindi nahi aati me sikh raha hu")

        elif 'hello how are you' in query:
            speak('i am fine what about you.')
            print("i am fine what about you.")

        elif 'i am also fine' in query:
            speak('thats nice. how can i help you')
            print("thats nice. how can i help you.")

        # elif 'how to solve rubiks cube' in query:

        # url = "https://ruwix.com/the-rubiks-cube/how-to-solve-the-rubiks-cube-beginners-method/step-4-yellow-cross/" 
        # webbrowser.open(url) 
        # speak('here you go')
        # print("here you go")


        elif 'say' in query:
           print(f"User said: {query}\n")


        elif 'i am fine' in query:
            speak('thats nice. any work for me sir')
            print("thats nice.")

        elif 'who are you' in query:
            speak('i am jarvis assistant created by yash.')
            print("i am jarvis assistant created by yash.")


        elif 'do i have any instagram messages' in query:
            speak('opening instagram')
            speak('no i think you all caught up')
            url = "http://www.instagram.com//" 
            webbrowser.open(url)

        elif 'thanks' in query:
            speak('its my job sir')
            print("its my job sir")

        elif 'open gaana' in query:
            speak('opening gaana')
            url = "http://www.gaana.com/" 
            webbrowser.open(url)

        elif 'open youtube' in query:
            speak('opening youtube')
            url = "http://www.youtube.com/" 
            webbrowser.open(url) 

        elif 'open google' in query:
            speak('opening google')
            url = "http://www.google.com/" 
            webbrowser.open(url) 

        elif 'open instagram' in query:
            speak('opening instagram')
            url = "http://www.instagram.com/" 
            webbrowser.open(url) 


        elif 'open stackoverflow' in query:
            speak('opening google')
            webbrowser.open("stackoverflow.com") 

        elif 'solution for my code' in query:
            speak('opening stackoverflow')
            webbrowser.open("stackoverflow.com")             


        elif 'play some music' in query:
            speak('playing music')
            music_dir = 'D:\song'
            songs = os.listdir(music_dir)
            print(songs)    
            os.startfile(os.path.join(music_dir, songs[0]))

        # file = "D:\song"
        # os.system("D:\song " + file)(can also use this)


        elif 'the time' in query:
            strTime = datetime.datetime.now().strftime("%H:%M:%S")    
            speak(f"Sir, the time is {strTime}")

        elif 'open code' in query:
            codePath = "C:\\Users\\yashs\\AppData\\Local\\Programs\\Microsoft VS Code\\Code.exe"
            os.startfile(codePath)

        elif 'email to yash' in query:
            try:
                speak("What should I say?")
                content = takeCommand()
                to = "yashsoni5104@gmail.com"    
                sendEmail(to, content)
                speak("Email has been sent!")
            except Exception as e:
                print(e)
                speak("sorry i am not able to send this email")
