# Peakvis-web
PeakVis is a visualization tool that syncronizes a given tweet dataset to a corresponding video of
a live broadcasted event. Its main features are: _(1)_ a responsive line graph that is directly linked to video playback time, which displays the volume of tweets at each moment of posting. _(2)_ automatic video highlight detection based on spikes of tweet volume. _(3)_ a message board that presents the top shared message at each timestep. _(4)_ a customizable, auto-updating wordcloud representation of what is being shared in the online s pace. Peakvis explores the relationship between live broadcasts and online user-generated content, enabling the analysis of broadcast highlights identified through Twitter posts peaks.

PeakVis is implemented in pure HTML/Javascript and works out-of-the-box in browser applications. Users can access it through the [Github Pages instance](https://davintlab.github.io/Peakvis-web/) or by downloading and running the release locally. 

## Citation

If you use Peakvis in a scientific publication, you may use the following citation:

```
@inproceedings{Peakvis2021,
    doi       = {10.1109/COMPSAC51774.2021.00065},
    year      = {2021},
    pages={418-427},
    author    = {Sanvido, Pedro Henrique M. and Kurtz, Gabriela B. and Teixeira, Carlos R. G. and Wagner, Pedro P. and Leuck, Lorenzo P. and Silveira, Milene S. and Tietzmann, Roberto and Manssour, Isabel H.},
    title     = {PeakVis: a Visual Analysis Tool for Social Network Data and Video Broadcasts},
    booktitle={2021 IEEE 45th Annual Computers, Software, and Applications Conference (COMPSAC)}
}
```


## Basic usage
![Usage1](https://i.imgur.com/fFApREy.png)

Peakvis expects two input files to be provided locally to function: a JSON file corresponding to tweet dataset, and an HTML5-supported video file of the recorded broadcast. Peakvis assumes the broadcast starts at the moment of the earliest post in the tweet dataset. As such, it is possible to adjust for time offsets by filling the Broadcast Start and Broadcast End fields following the `YYYY-MM-DD HH:mm:SS` convention. The highlight sensitivity range selector determines how likely Peakvis is to mark a "peak" as a highlight.

## Tweet volume line chart

- Plots the number of tweets at each second in time in a line chart.
- The line chart is synced to video playback time: watched segments are colored blue, and any seek operations are synced automatically.
- Starting point of tweet peaks are indicated by the purple markers.

![alt text](https://media.discordapp.net/attachments/511284977409851402/725465708909035590/unknown.png?width=1442&height=299)

### Tweet display box

- While the video is playing, the rightmost box displays the textual contents of tweets at broadcast time.
- One tweet is displayed at each time (if there are any tweets at the exact timeframe).
- If there are multiple tweets in a given timeframe, the most retweeted one is displayed instead.
- Tweets also may be accessed directly by clicking the hyperlink provided.

![alt text](https://media.discordapp.net/attachments/830590281966682193/842865515357798460/tweets.png)

## Tweet wordcloud

- Playing on the idea of providing context at any given time, Peakvis draws a wordcloud of frequently said words.
- Stopword removal and general cleaning procedures are performed in this step.
- In _cumulative mode_, the wordcloud is drawn from the starting point of the video, up to the current playback time. Going further in playback time just appends more words to the current word pool.
- The _sliding window_ mode takes a look back and a look ahead (minutes) value, and the wordcloud is drawn from the interval created from these values according to current playback time.
- Max words: maximum number of words in the wordcloud.
- Step: the wordcloud is updated at every step (seconds).
- The current wordcloud controls placeholder and likely to be changed in future versions.

![alt text](https://i.imgur.com/UocJgwS.png)



