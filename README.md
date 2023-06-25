import openai
import pyttsx3
import wikipedia
import webbrowser
import random
import time
import tkinter as tk
from tkinter import*
from PIL import ImageTk, Image
import subprocess
from datetime import date

def m(text):
  
  label = tk.Label(root, text="MARK A.I:  "+ text)
  label.place(x=10, y=600)
  label.pack()
  engine = pyttsx3.init()
  engine.setProperty('rate', 170)  # Speed of speech (words per minute)
  engine.setProperty('volume',1)  # Volume level (0.0 to 1.0)
  engine.say(text)
  engine.runAndWait()
              
today = date.today()

#main code

def open_application(application_path):
    subprocess.Popen([application_path])
  
         
 



            
def main_code():
          
        j = entry.get()
        text.insert(tk.END,"you:"+ j + "\n")
        
        if "hi" in j:
            o=("hello sir","hi sir")
            m(random.choice(o))
        elif 'date'    in j:
          m(today)
        elif 'okay' in j:
            m("fine sir")
        elif "hello" in j:
            o=("hello sir","hi sir")
            m(random.choice(o))
        elif 'play song' in j :
            s=['https://youtu.be/wy709iNG6i8','https://youtu.be/bV5z_rVR6Ms']
            m("playing your song")
            webbrowser.open(random.choice(s))
            
        elif "who is your developer" in j:
            m("Atulya Ajay Singh,is my developer and creator")
        elif "who is your creator" in j:
            m("Atulya Ajay Singh,is my developer and creator")
        elif "exit" in j:
            m("closing A.I in 3 seconds....")
            time.sleep(3)
            exit()
        elif "how are you" in j:
            m("i am fine sir")
        elif 'search' in j:
            j=j.replace('search','')
            m("searching")
            m(j)
            y= ' https://www.google.com/search?q=atulya'
            t=y.replace("atulya",j)
                        
            webbrowser.open(t)
                           
        elif"fuck"  in j:
            m("sir,dont use abusing language to conversate with me")
            
        elif"ass"in j:
            m("sir,dont use abusing language to conversate with me")
        elif "app" in j:
            
            j=j.replace("app ","")
            w= r"C:/Windows/system32/c.exe"
            p=w.replace("c",j)
            
        
            application = p
            open_application(application)
 
        
        elif "open" in j:
            j=j.replace("open ","")
            m("opening")
            m(j)
            time.sleep(2)
            p= ("https://www.example.com")
            p=p.replace("example",j)
                                   
            
            webbrowser.open(p)                                 
        elif "wikipedia" in j:
            m("searching....")
            j=j.replace("wikipedia","")
            results=wikipedia.summary(j)
            
          
            
            m("acording to wikipedia")
            m(results)
            time.sleep(3)
        elif "gpt" in j:
             openai.api_key = 'sk-M78agllHVtuTk9NjfBMmT3BlbkFJKscH5dd3P8y3It2ArjAQlcc'
             response = openai.Completion.create(
             engine='davinci',
             prompt='Once upon a time',
             max_tokens=100
             )
             gengerated_text = response.choices[0].text.strip()
             m(generated_text)
        else:
            m("sir i can't understand what you are trying to say ")
            
 
            

root = Tk()

# Load the image using PIL
 

# Create a Label widget for the text
text_label = Label(root, text="MARK A.I", font=("Arial", 16), bg="white")
text_label.place(x=10, y=10)  # Adjust the coordinates to position the text

# Run the Tkinter event loop


entry = tk.Entry(root)
entry.place(x=500,y=120)
entry.pack()

button = tk.Button(root, text="ENTER", command=main_code)
button.pack()

label = tk.Label(root, text="")
label.pack()
text = tk.Text(root)
text.pack()

root.mainloop()
     
  
