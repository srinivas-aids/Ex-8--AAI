<H1 ALIGN =CENTER>Implementation of Speech Recognition</H1>
<H3>NAME: srinivas u</H3>
<H3>REGISTER NO: 212221230108</H3>
<H3>EX. NO.8</H3>
<H3>DATE: </H3>
<H3>Aim:</H3> 
To implement the conversion of live speech to text.<BR>
<h3>Algorithm:</h3>

1. Import the speech_recognition library
2. Initialize the Recognizer
3. Create an instance of the Recognizer class, which will be used for recognizing speech.
4. Set the duration for audio capture
5. Define a variable to specify the duration (in seconds) for which the program will capture audio from the microphone
6. Display a message in the console to prompt the user to speak.
7. Capture audio from the default microphone
8. Use the default microphone as the audio source.
9. Record audio for the specified duration using the Recognizer instance.
10. Perform speech recognition with exceptional handling:
    
    -	Attempt to recognize speech from the captured audio using the Google Speech Recognition service.
    -	If successful, print the recognized text.
    -	Handle specific exceptions: If the recognition result is unknown or if there is an issue with the request to the Google Speech Recognition service, print corresponding error messages.
    -	A generic exception block captures any other unexpected errors.
    
<H3>Program:</H3>

```py
import speech_recognition as sr
r = sr.Recognizer()

duration = 5

with sr.Microphone() as source :
    print("Say something:\n\n")
    audio_data = r.listen(source,timeout = duration)

try:
    text = r.recognize_google(audio_data)
    print("You said:\n", text)
except sr.UnknownValueError:
    print("Sorry, could not understand audio")
except sr.RequestError as e:
    print(f'Error with the request to Google Speech Recognition service: {e}')
except Exception as e:
    print(f'Error: {e}')
```

<H3> Output:</H3>

![image](https://github.com/user-attachments/assets/755a4a05-318b-4924-8585-464e4d481268)

<H3> Result:</H3>

Thus, we have implemented a program to transcribe the audio file in the file variable and print the transcribed text on the console, one line at a time.
