## Introduction to Neuromarketing
**Neuromarketing** :- making the subconscious as conscious.
People lie themselves, like they say they want something but they act in a different way and purchase something else. There are several times when people go to superstores to buy some item but end up purchasing several other items but the intended one.

So generally people lie to themselves almost all the time which may be conscious or subconscious, so can we rely on surveys and opinions of customers.Neuromarketing takes an edge over several other marketing measures since it provides insight into automatic responses that take place at the **subconscious level**.

Important insights from neuromarketing strategies that align with our own experiences and beliefs:

- Emotions drive biases and subconscious decision-making.
- Visuals are processed more quickly than words.
- Images of celebrities, beautiful women, children and puppies are universally appealing.
- Faces of any type draw the eye better than other kinds of visuals, and convey important emotional information such as mood, status, etc.
- Messages that consumers find irrelevant reduce their positive responses. Marketing elements that consumers can personally identify with create a positive response.
- When a consumer purchases a product from a brand he or she is loyal to, the reward center of the brain gets activated.
- Prices with round numbers (like Rs 100) are processed more easily, yet numbers like Rs 99.99 are perceived as a better deal.
- Certain colors elicit particular emotional reactions.
- The first and last parts of a message are especially important in setting the context for how a message is perceived.
- Social norms such as reciprocity can be invoked to influence behavior.
- Avoiding pain is often a stronger motivator than seeking pleasure


Neuromarketing is a new and evolving science that can help marketers better understand consumer behavior in order to improve their:
- Packaging
- Pricing
- Brand positioning
- Promotion strategies
- New product development

## About the Dataset
In this Project, I have worked upon detection of emotions from the EEG signals which have been taken from the SJTU Emotion EEG Dataset(SEED). This dataset contains emotions of people as per the EEG signal received when they were shown clips of movie trailers.

### How the experiment was conducted?
15 Chinese film clips (positive, neutral and negative emotions) were chosen from the pool of materials as stimuli used in the experiments. The selection criteria for film clips are as follows: (a) The length of the whole experiment should not be too long in case it will make subjects fatigue. (b) The videos should be understood without explanation (c) The videos should elicit a single desired target emotion.

### Arrangement of the experiment
The duration of each film clip is about 4 minutes. Each film clip is well edited to create coherent emotion eliciting and maximize emotional meanings. There are totally 15 trials for each experiment. There is a 5s hint before each clip, 45s for self-assessment and 15s for rest after each clip in one session. The order of presentation is arranged so that two film clips targeting the same emotion are not shown consecutively. For the feedback, participants are told to report their emotional reactions to each film clip by completing the questionnaire immediately after watching each clip. The detailed protocol is shown below:

![image](https://user-images.githubusercontent.com/75975560/124713801-9cf13b00-df1e-11eb-92fd-018c7bd726ee.png)

### Subjects
Fifteen Chinese subjects (7 males and 8 females; MEAN: 23.27, STD: 2.37) participated in the experiments. In order to protect personal privacy, we have hidden their names and indicate each subject with a number from 1 to 15.

## Problem Statement
So since I described earlier that I have been provided with the EEG signals from brainwave scans having **2548 electrodes** each having an activity measured in microVolts and there's another column which is the prediction column containing emotions as **Positive,Negative or Neutral** That literally means that we currently have **2549 columns**. Isn't that a huge number?

The flow of this Analysis has been decided to be:

First I have imported the dataset of SEED EEG emotions from my local directory.

I then used **wavelet transform** to my signals which decomposes a waveform into a set of wavelets and is highly recommended when dealing with signals having short intervals of characteristic oscillations. I even tried **Fourier Transform** but it didn't seem to work probably because it's not good with signals having short intervals of characteristic oscillations since it captures global frequency information, meaning frequencies that persist over an entire signal which doesn't hold good for these signals After wavelet transform my signal reduced from **2548** electrode signals to a mere **319** signals which is a tremendous dimensionality reduction too.

Then I utilised **Recursive Feature Elimination** which works as follows:- Select features by recursively considering smaller and smaller sets of features. First, the estimator which I have taken to be Random Forest is trained on the initial set of features and the importance of each feature is obtained either through any specific attribute or callable. Then, the least important features are pruned from current set of features. That procedure is recursively repeated on the pruned set until the desired number of features which I have set as **10** to select is eventually reached. So now I have made my features as only 10 columns of signals, this is a huge transition from **2548 to 319 to 10**.

Next step is the train test split done as 70-30 ratio

I made it as a supervised learning problem, labels are predicted using predictors andd built a model consisting of only an LSTM and a Dense Layer. So model was trained and validated and it predicted emotions with 89.5 % accuracy on the test set.

In the Last step,I plotted a confusion matrix and a classification report which indicates 89% for both precision and recall and hence f1 score.
