# ML-Fake_News_Stance_Detect
Fake news detection with stance in Consideration

# Plan

## Stage 1 (Stance Detection) (Done)
* http://www.aclweb.org/anthology/N16-1138
* https://www.ijcai.org/proceedings/2017/0557.pdf
* http://www.fakenewschallenge.org/
* https://arxiv.org/abs/1708.05286
* https://web.stanford.edu/class/cs224n/reports/2760496.pdf

OK, BUT WHAT DOES STANCE DETECTION HAVE TO DO WITH DETECTING FAKE NEWS?
ANSWER:
There are two important ways the Stance Detection task is relevant for fake news.

From our discussions with real-life fact checkers, we realized that gathering the relevant background information about a claim or news story, including all sides of the issue, is a critical initial step in a human fact checker’s job. One goal of the Fake News Challenge is to push the state-of-the-art in assisting human fact checkers, by helping them quickly gather the information they need to make their assessment.

In particular, a good Stance Detection solution would allow a human fact checker to enter a claim or headline and instantly retrieve the top articles that agree, disagree or discuss the claim/headline in question. They could then look at the arguments for and against the claim, and use their human judgment and reasoning skills to assess the validity of the claim in question. Such a tool would enable human fact checkers to be fast and effective.

It should be possible to build a prototype post-facto “truth labeling” system from a “stance detection” system. Such a system would tentatively label a claim or story as true/false based on the stances taken by various news organizations on the topic, weighted by their credibility.

For example, if several high-credibility news outlets run stories that Disagree with a claim (e.g. “Denmark Stops Issuing Travel Visas to US Citizens”) the claim would be provisionally labeled as False. Alternatively, if a highly newsworthy claim (e.g. “British Prime Minister Resigns in Disgrace”) only appears in one very low-credibility news outlet, without any mention by high-credibility sources despite its newsworthiness, the claim would be provisionally labeled as False by such a truth labeling system.

In this way, the various stances (or lack of a stance) news organizations take on a claim, as determined by an automatic stance detection system, could be combined to tentatively label the claim as True or False. While crude, this type of fully-automated approach to truth labeling could serve as a starting point for human fact checkers, e.g. to prioritize which claims are worth further investigation.

### Datasets
* https://github.com/FakeNewsChallenge/fnc-1


## Stage 2 (Text body summarization + Similar or Not)
My idea here is to run the body of a news through text summarization model that will produce a headline.
Then run text similarity between the given headline and the summarization. We should use some kind of transfer learning here.
### Dataset
* https://github.com/dhwajraj/deep-siamese-text-similarity
* https://www.kaggle.com/sunnysai12345/news-summary

## Stage 3 (Irony or not) (Used as a feature)
A genuine news article should not be a irony (or should not contain mainly irony sentences)
### Dataset
* https://competitions.codalab.org/competitions/17468

## Stage 4 (Fake news classification ( Fake or Not))
## Datasets
* https://www.kaggle.com/jruvika/fake-news-detection/data
* https://www.kaggle.com/mrisdal/fake-news/data
* https://github.com/several27/FakeNewsCorpus

## Stage 5 (Topic classification based on heading (done), topic classification based on the summary, topic modeling of the content)

The main purpose of this model is to classify the topics into 4 categories (more info at https://www.kaggle.com/uciml/news-aggregator-dataset)
We can run the same classificator on the summary (the classificator was trained on short texts, but should experiment with longer). If we get different topics the news might not be trustworthy but a clickbait. We can run also unsupervised machine learning (LDA) to get topics.

