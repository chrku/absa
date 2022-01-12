# ABSA - Aspect-Oriented Sentiment Analysis

Aspect-Oriented Sentiment Analysis or Aspect Based Sentiment Analysis (ABSA) is an NLP task. It is a more fine-grained version of the sentiment analysis task. In sentiment analysis, the task is to find out whether a given piece of text has a certain polarity, i.e. to find out whether it has a certain sentiment. An example is "the food is bad", which has a negative sentiment. This is a special case of text classification. This kind of task can come up in many applications, e.g. in processing reviews from customers to gauge customer satisfaction.

ABSA extends this task; here, we want to know what exactly is being judged as positive, negative or neutral and we may have different parts of the sentence with different polarities. For example, in "the food is bad, but the service was OK", we would have to both extract "the food" and "the service" as aspects and we would also have to determine that the polarity of both of these aspects; i.e. find out that "the food" is negative and "the service" is neutral.

ABSA can be split into two distinct subtasks - aspect extraction (AE) and aspect-level sentiment classi􏰁cation (ALSC). The first deals with finding aspects, while the second deals with determining the polarity of those aspects. Many approaches treat these separately and then use a pipelined approach, while others offer unifed end-to-end solutions.

We chose to explore the ABSA problem based on the SemEval 2014 Task 4 dataset. This is a labeled dataset for ABSA, with two problem domains being available - laptop and restaurant reviews. The dataset is given as a collection of XML files. Below, we show a training example:

```
<sentence id="2339">
 <text>I charge it at night and skip taking the cord with me because of the good -
 battery life.</text> <aspectTerms>
 <aspectTerm term="cord" polarity="neutral" from="41" to="45"/>
 <aspectTerm term="battery life" polarity="positive" from="74" to="86"/> </aspectTerms>
</sentence>
```

## Model

We built an ABSA model on top of a HuggingFace transformer, which we show in the attached Jupyter notebook. 
