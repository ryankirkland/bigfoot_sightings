# Decrypting the Cryptid

<img src='https://github.com/ryankirkland/bigfoot_sightings/blob/master/img/egzHWiazUP6AYkyF4ECjJP.jpg'>

## Overview

The goal for this analysis is to uncover trends in bigfoot sighting data from BFRO.net.

## The Data

The supplied data was html content from bigfoot sighting submission web pages stored in JSON:

#### Raw Data:
<img src='https://github.com/ryankirkland/bigfoot_sightings/blob/master/img/og.png'>

Using BeautifulSoup, the data was parsed into useful subsections for EDA:
#### DataFrame:
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
