# Emotion Based AI Recommender
## Steps Followed
- A pretrained VGG-16 network architecture was used with some modification to predit emotion of a person which can be one of **{'Anger', 'Neutral', 'Fear', 'Happiness', 'Sadness', 
'Surprise'}**. This model scored well on performance metrics and its .h5 file was created.
- I used HTML and CSS to create a frontend for webapp. This frontend worked as follows:
#### First page asks the user to enter the language in which he/she wants to hear the song which can be English,Hindi,Punjabi or any other choice. 
![image](https://user-images.githubusercontent.com/75975560/124743587-81e0f400-df3b-11eb-9d7f-a79d1c699912.png)
![image](https://user-images.githubusercontent.com/75975560/124743688-991fe180-df3b-11eb-9a99-530109a9ba6d.png)
#### I clicked Hindi in Language so its color changed
#### Second page asks the user to enter his/her singer from the list or any other whose song he/she wants to hear.
![image](https://user-images.githubusercontent.com/75975560/124743815-b8b70a00-df3b-11eb-8050-7caed32f6ee2.png)
![image](https://user-images.githubusercontent.com/75975560/124743865-ca98ad00-df3b-11eb-955e-7f68aa9f1b65.png)
#### I clicked Arijit Singh hence changing its color.
#### Now using OpenCV, the camera opens and capatures the face of the person present which is sent to our trained model which ultimately predicts the emotion of the person.
![image](https://user-images.githubusercontent.com/75975560/124745355-5b23bd00-df3d-11eb-8a36-f79d7df88a14.png)
#### The recommendations page we get after clicking 'Click Here to get your Personalised Recommendation', looks like
![image](https://user-images.githubusercontent.com/75975560/124746142-29f7bc80-df3e-11eb-80aa-445a178d3cc8.png)
#### which is actually the link
https://www.youtube.com/results?search_query=arijit+singh+heartbroken+Hindi+song
#### Now recommended songs are opened on youtube for the person as per his/her choices and emotion. Like romantic songs if happy, heartbroken songs if sad or party songs etc.
