# Peakvis
PeakVis is a visualization tool that syncronizes a given tweet dataset to a corresponding video of
a live broadcasted event. Its main features are: _(1)_ a responsive line graphs that is directly linked to video playback time, which displays the volume of tweets at each moment of posting. _(2)_ automatic video highlight detection based on spikes of tweet volume. _(3)_ a message board that presents the top shared message at each timestep. _(4)_ a customizable, auto-updating wordcloud representation of what is being shared in the online s pace. Peakvis explores the relationship between live broadcasts and online user-generated content, enabling the analysis of broadcast highlights identified through Twitter posts peaks.

PeakVis is implemented in pure HTML/Javascript and works out-of-the-box in browser applications. Users can access it through the [Github Pages instance](https://davintlab.github.io/Peakvis-web/) or by downloading and running the release locally. 

## Usage
![Usage1](https://i.imgur.com/fFApREy.png)

Peakvis expects two input files to be provided locally to function: a JSON file corresponding to tweet dataset, and an HTML5-supported video file of the recorded broadcast. Peakvis assumes the broadcast starts at the moment of the earliest post in the tweet dataset. As such, it is possible to adjust for time offsets by filling the Broadcast Start and Broadcast End fields following the `YYYY-MM-DD HH:mm:SS` convention. The highlight sensitivity range selector determines how likely Peakvis is to mark a "peak" as a highlight.

