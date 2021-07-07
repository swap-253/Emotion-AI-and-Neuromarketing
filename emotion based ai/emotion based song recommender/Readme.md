# Emotion Based AI Recommender
## Steps Followed
- A pretrained VGG-16 network architecture was used with some modification to predit emotion of a person which can be one of **{'Anger', 'Neutral', 'Fear', 'Happiness', 'Sadness', 
'Surprise'}**. This model scored well on performance metrics and its .h5 file was created.
- I used HTML and CSS to create a frontend for webapp. This frontend worked as follows:
a) First page asks the user to enter the language in which he/she wants to hear the song which can be English,Hindi,Punjabi or any other choice. 
b) Second page asks the user to enter his/her singer from the list or any other whose song he/she wants to hear.
c) Now using OpenCV, the camera opens and capatures the face of the person present which is sent to our trained model which ultimately predicts the emotion of the person.
- Now recommended songs are opened on youtube for the person as per his/her choices and emotion. Like romantic songs if happy, heartbroken songs if sad or party songs etc.
