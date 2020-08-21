# Decrypting the Cryptid

<img src='https://github.com/ryankirkland/bigfoot_sightings/blob/master/img/egzHWiazUP6AYkyF4ECjJP.jpg'>

## Overview

The goal for this analysis is to uncover trends in bigfoot sighting data from BFRO.net.

## Tools & techniques featured in this project
- Tools: Python, Jupyter Notebook, Pandas,Beautiful Soup, SkLearn, SciPy, PlotLy
- Techniques: Data wrangling, EDA, NLP, KNN, K-Means

## The Data

### Text ingestion
### Source selection
The supplied data was html content from bigfoot sighting submission web pages stored in JSON.
We chose to use this data. We looked for other sources, but found that the publishers of this information took the most care to be most credible. A team of researchers would follow up on each sighting with an interview and collection of 'evidence' and attempt to consistently classify the report. They only publish the top three tiers of credibility--A through C in order of most to least evidence.

### Data import and data wrangling
<img src='https://github.com/ryankirkland/bigfoot_sightings/blob/master/img/og.png'>

Using BeautifulSoup, the data was parsed into useful subsections for EDA.
Data was pretty messy--think of looking through a filing cabinet for a document where the person who was in charge of filing didn't reliably put files in the right folders.
Straightened out the filing cabinet and then obtained relevant time, geographic, and qualitative information.

<img src='https://github.com/ryankirkland/bigfoot_sightings/blob/master/img/df.png'>

## EDA

The examination was a grouping of classification type.

#### Classification Totals
<img src='https://github.com/ryankirkland/bigfoot_sightings/blob/master/img/class.png'>

Classifications Defined:

<div>
  <p>
    - <b>Class A:</b> Reports involve clear sightings in circumstances where misinterpretation or misidentification of other animals can be ruled out with greater confidence. For example, there are several footprint cases that are very well documented. These are considered Class A reports, because misidentification of common animals can be confidently ruled out, thus the potential for misinterpretation is very low.
  </p>
  <p>
    - <b>Class B:</b> Incidents where a possible sasquatch was observed at a great distance or in poor lighting conditions and incidents in any other circumstance that did not afford a clear view of the subject are considered Class B reports.

For example, credible reports where nothing was seen but distinct and characteristic sounds of sasquatches were heard are always considered Class B reports and never Class A, even in the most compelling "sound-only" cases. This is because the lack of a visual element raises a much greater potential for a misidentification of the sounds.

Class B reports are not considered less credible or less important than Class A reports--both types are deemed credible enough by the BFRO to show to the public. For example, one of the best documented reports ever received by the BFRO is a Class B report from Trinity County California. It involved a very credible witness who backpacked into a remote area that has a history of sasquatch-related incidents. He described various occurrences around his camp at night that are strongly suspected to be sasquatch-related. The report is still considered Class B though because there was no clear visual observation to confirm what was heard outside the tent.
  </p>
  <p>
  - <b>Class C:</b> Most second-hand reports, and any third-hand reports, or stories with an untraceable sources, are considered Class C, because of the high potential for inaccuracy. Those reports are kept in BFRO archives but are very rarely listed publicly in this database. The exceptions are for published, or locally documented incidents from before 1958 (before the word "Bigfoot" entered the American vocabulary), and sightings mentioned in non-tabloid newspapers or magazines.
  </p>
</div>

#### Submissions by Measures of Time

While the day of week for submissions were all fairly similar, it appears people most commonly submit sightings on Sunday and Monday - likely after a weekend hiking or hunting trip:

<img src='https://github.com/ryankirkland/bigfoot_sightings/blob/master/img/dayofweek.png'>

As expected, Summer is the leading season for submissions, as it is the most popular time for outdoor activities, followed by Fall:

<img src='https://github.com/ryankirkland/bigfoot_sightings/blob/master/img/seasons.png'>

Interestingly, submissions of bigfoot sightings peaked in the early 2000s, continuing to trail down as we get closer to today:

<img src='https://github.com/ryankirkland/bigfoot_sightings/blob/master/img/year.png'>

#### Geographic distribution of sightings
A map of total sightings by county was created to show where sightings have occurred.

<img src='https://github.com/ryankirkland/bigfoot_sightings/blob/master/img/bigfoot_map.png'>

Given that bigfoot doesn't abide by county boundaries, we regionalized the data using a KNN model. This creates a 'prediction' of where to look for bigfoot.

<img src='https://github.com/ryankirkland/bigfoot_sightings/blob/master/img/bigfoot_prediction.png'>

These maps utilized total sightings recorded. Where have the most recent sightings occurred?

<img src='https://github.com/ryankirkland/bigfoot_sightings/blob/master/img/state_last_10.png'>

#### Text preprocessing--functions and methods
- Machine learning models need to have text converted into a format that they can use. 
- The steps we took to turn the text into machine-readable 'data' included stripping punctuation, tokenizing, lemmatization, and removing stopwords.
- We then 'vectorized' each observation so that the models could compare them.

#### Are there any patterns to what people said in their bigfoot sighting reports?

We wanted to look at the text of the reports themselves to see if they fit into obvious groups. Once we had our text in the right format, it was easy to apply a few different machine learning models to analyze the text. The two primary models we used were K-Means and NMF. 

K-Means was used to try to group the collection of observations into 5 different groupings based upon common words and their frequency. The model outputs the most important words it found for each group.

<img src='https://github.com/ryankirkland/bigfoot_sightings/blob/master/img/kmeans_raw.png'>

NMF was used to determine any potential topics from the observations - the results from NMF unveiled similar topics to those found from the K-Means clustering.

<img src='https://github.com/ryankirkland/bigfoot_sightings/blob/master/img/raw_nmf.png'>



