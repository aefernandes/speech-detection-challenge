Please clone this repository and push your work to your own GitHub account. To submit, send us a link to your final repository on GitHub, containing all code and answers for Parts 1 and 2. 

Please use best practices in version control. Feel free to use whatever you believe are the best tools for the job. If you do any independent research, please cite your sources. We anticipate this task will take 5-6 hours to complete. 

After submission, we will schedule time to review your code and analysis with a member of our team. If you have any questions, reach out to afernandes @ schmidtfutures . com. We look forward to discussing this with you!

# Part 1: Feature Extraction

You are given three 5-minute audio snippets of a child playing with its mother. These are recordings from a natural home environment. 

## Task 
Your challenge is to extract the audio features you believe are most important to distinguish between child and adult speech. This should be a set of independent features that are robust to who the speaker is and to environmental noise.

Submit your code, the final dataset of extracted features, and answers to the questions below. 

## Questions
1. What audio features did you choose to extract and why?
2. Are there any features you intentionally didn't use? 
3. What steps did you take to transform the original .wav files to prepare for feature extraction?
4. How well do you think this audio reflects real-world conditions? What types of sounds might be harder to handle, and what edge cases would you prioritize detecting or filtering first?
5. Is there anything you would want to add, optimize, or improve if you had more time?
6. If you were to annotate these audio files to train a supervised learning model, what labels would you include? Assume each row of the dataset represents a 10-second audio snippet, and provide an example column header. 

# Part 2: Modeling

Our work focuses on identifying child and adult voices, but in this example, we'd like you to train a model to determine the gender of a voice. Voice samples were collected from a variety of open source resources and stored as .WAV files, which were pre-processed for acoustic analysis. `voices.csv` is a file containing 3168 rows and 21 columns (20 columns for each feature and one label column for the classification of male or female). 

It measures the following acoustic properties: 
- duration: length of signal
- meanfreq: mean frequency (in kHz)
- sd: standard deviation of frequency
- median: median frequency (in kHz)
- Q25: first quantile (in kHz)
- Q75: third quantile (in kHz)
- IQR: interquantile range (in kHz)
- skew: skewness (see note in specprop description)
- kurt: kurtosis (see note in specprop description)
- sp.ent: spectral entropy
- sfm: spectral flatness
- mode: mode frequency
- centroid: frequency centroid (see specprop)
- peakf: peak frequency (frequency with highest energy)
- meanfun: average of fundamental frequency measured across acoustic signal
- minfun: minimum fundamental frequency measured across acoustic signal
- maxfun: maximum fundamental frequency measured across acoustic signal
- meandom: average of dominant frequency measured across acoustic signal
- mindom: minimum of dominant frequency measured across acoustic signal
- maxdom: maximum of dominant frequency measured across acoustic signal
- dfrange: range of dominant frequency measured across acoustic signal
- modindx: the accumulated absolute difference- between adjacent measurements of fundamental frequencies divided by the frequency range

## Task
Your challenge is to build a model to detect the gender of a voice. Always predicting "male" will achieve 50% accuracy. Our naive model based strictly on average dominant frequency achieves accuracy of 61% on training data and 59% on test data. We expect you can do significantly better.

1. Determine which properties are statistically significant for determining gender. Report your results.
2. Build a full logistic regression model and evaluate its performance. Report your results, including accuracy on the training and test set.
3. Train any model of your choice to achieve an accuracy above 80%. 

Submit code for all three portions above, as well as any screenshots or plots you create. In addition, please answer the questions below. 

## Questions
1. What changes did you make in Section 3 to increase the accuracy of your ML model? Include a description of features you selected or created, parameters you tuned, and a discussion of tradeoffs.
2. Is there anything you would want to add, optimize, or improve if you had more time?
3. How might the model you built perform in the real world? What technical or ethical considerations would you weigh when deciding whether to deploy such a system?
4. What would you do differently if you were trying to detect adult vs. child speech instead of male vs. female voices?

# Evaluation

You will be evaluated on: 
- the relevance of the features you extract
- the accuracy of your models
- the readability of your code
- your ability to pick an appropriate model or technique for a task and your understanding of their relative merits
- the quality of your explanations 

