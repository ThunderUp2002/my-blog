---
layout: post
title:  "Fall Fanatics, Pt. II: There's an App for That"
date: 2024-12-04
author: Devan Gwynn
description: "An overview of the web app I developed to enable quick EDA of fall college sports data"
---

<p class="intro"><span class="dropcap">I</span>f you read my last post, you know how much I love college sports, particularly those in the fall. Last time, I curated a dataset that contains team stats for metrics in football, women's volleyball, and women's soccer with the goal of determining which schools have had the best performance across all three sports this season, as well as comparing Power Four conferences and how BYU stacks up in that realm. Well following my last post, I built a web app that lets users quickly and easily examine different aspects of the dataset so you can make your own findings. Let's get into it!</p>

### College Sports Stats

The <a href="https://college-sports.streamlit.app/" target="_blank">app</a> was built using Streamlit. It contains four tabs:
1. Overall
2. Football
3. W Volleyball
4. W Soccer

As you can see, each tab is designed to focus on a specific sport (or the overall performance). I will now briefly explain the features of each tab.

#### Overall

Within the overall tab are three options:

<dl>
  <dt>All</dt>
  <dd>Displays a histogram of the distribution of average z-score for all colleges</dd>
  <dt>Conference</dt>
  <dd>Displays KDE plot of average z-score distribution for selected conference(s)</dd>
  <dt>College</dt>
  <dd>Displays all team stats for the selected college</dd>
</dl>

These hierarchical options allow you to dive deeper on any level you want--whether that be looking more generally at all teams or more specifically at a single team. Using these options, you can fine-tune how much information you would like to look at.

#### Football, W Volleyball, and W Soccer

Each of these tabs is laid out with the same format. Immediately after clicking on the tab, a histogram of the distribution of the appropriate metric for all teams is shown. You then have the option to select one or more Power Four conferences, enabling flexible and dynamic filtering. Conferences that are selected will be shown on the KDE plot, allowing you to compare and contrast various conferences. Additionally, a table providing the data used to create the plot can optionally be viewed.

### Key Insights

In the process of working with this data, I have come across many different notable observations. Here are just two I'd like to share and briefly elaborate on:

1. The Power Four conferences have varying levels of balance

<figure>
	<img src="{{site.url}}/{{site.baseurl}}/assets/img/2024-11-13-eda/average-z-score-distribution-by-conference.png" alt=""> 
</figure>

You may recall from my last post:

<blockquote>The SEC and ACC appear to be fairly balanced conferences in these sports, with less disparity in skill among their teams displayed by the roughly symmetric distribution. On the other hand, the Big Ten and Big 12 appear to be somewhat imbalanced, as can be seen by the odd bulges in their distributions.</blockquote>

While it makes sense that the Power Four conferences can be unbalanced, it makes you wonder if those pushing for a promotion/relegation system (where teams get promoted or relegated based on their performance) in college sports have a point, since that would likely rebalance the competition by sorting colleges into tiers. This also becomes evident as you look at each conference's performance across the different sports.

2. Different Power Four conferences are stronger in different sports

| Conference  | +/- GPG | +/- Hitting % | +/- PPG | Average z-Score |
| ----------- | ------- | ------------- | ------- | --------------- |
| ACC         | 0.72    | 0.04          | 6.12    | 0.51            |
| Big Ten     | 0.36    | 0.03          | 5.58    | 0.36            |
| Big 12      | 0.35    | 0.03          | 4.53    | 0.31            |
| SEC         | 0.7     | 0.04          | 10.23   | 0.64            |

Also from my last post:

<blockquote>The table shows about what we would expect: ACC and SEC being best in soccer and football, while the spread in volleyball is much tighter. Based on these statistics, the SEC is the best conference overall in these three sports, followed by the ACC, the Big Ten, and finally the Big 12.</blockquote>

It would be interesting to see how balanced each conference is within the sport in which it has the strongest performance. That would show whether it's just the top teams inflating the conference's numbers or if the conference as a whole really is better at that sport.

### Conclusion

Overall, we've discovered some insightful observations about Power Four conferences--both regarding the variation of strength within each one as well as which conferences are more successful in which sports. However, these are just a drop in the bucket of data exploration. Using the app should make the EDA process fairly straightforward and quick for several different tasks. Take a look at some of the features, and let me know about any interesting findings!

*The code for my app can be found <a href="https://github.com/ThunderUp2002/data-curation" target="_blank">here</a>.*