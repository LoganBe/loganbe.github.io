---
layout: default
title: Data_Projs
permalink: /data_projs/
---

<h1 class="text-start"> Data Project #1: Analysis of Student Activities on Grades and Stress </h1>
#### Data source: <a href="https://www.kaggle.com/datasets/steve1215rogg/student-lifestyle-dataset" target="_blank" rel="noopener noreferrer">Kaggle Data Set</a>

<div class="container-fluid p-0 m-0 mb-4">
Students’ academic performance and stress levels are shaped by a range of interconnected factors, including study habits, sleep quality, participation in extracurricular activities, physical exercise, and social interactions. Understanding how these elements contribute to both grades and stress is crucial for developing strategies to support student well-being and success. In the following analysis, I investigate the impact of these variables on student outcomes using survey data collected from approximately 2,000 primarily Indian students over the academic year spanning August 2023 to May 2024. This dataset provides a comprehensive view of students’ experiences and behaviors, allowing for an in-depth exploration of the relationships between lifestyle factors, stress, and academic achievement.
</div>

## Raw Data Statistics and Visualizations
<div class="container my-4 mb-4">
  <div class="row">
    <!-- Left Column: Table -->
    <div class="col-md-6 d-flex align-items-stretch">
      <table class="table table-bordered table-sm w-100 mb-0 align-self-stretch">
        <thead class="table-light">
          <tr>
            <th>Feature</th>
            <th>Min</th>
            <th>Max</th>
            <th>Median</th>
            <th>Average</th>
            <th>Std</th>
          </tr>
        </thead>
        <tbody style="height: 100%;">
          <tr style="height: 16.66%;"><td>Study (hours)</td><td>5.0</td><td>10.0</td><td>7.4</td><td>7.48</td><td>1.42</td></tr>
          <tr style="height: 16.66%;"><td>Extracurricular (hours)</td><td>0.0</td><td>4.0</td><td>2.0</td><td>1.99</td><td>1.16</td></tr>
          <tr style="height: 16.66%;"><td>Sleep (hours)</td><td>5.0</td><td>10.0</td><td>7.5</td><td>7.50</td><td>1.46</td></tr>
          <tr style="height: 16.66%;"><td>Socia (hours) </td><td>0.0</td><td>6.0</td><td>2.6</td><td>2.7</td><td>1.69</td></tr>
          <tr style="height: 16.66%;"><td>Physical (hours)</td><td>0.0</td><td>13.0</td><td>4.1</td><td>4.33</td><td>2.51</td></tr>
          <tr style="height: 16.66%;"><td>Grade (GPA)</td><td>2.24</td><td>4.0</td><td>3.11</td><td>3.12</td><td>0.30</td></tr>
        </tbody>
      </table>
    </div>

    <!-- Right Column: Image -->
    <div class="col-md-6 d-flex align-items-center justify-content-center mb-4">
      <img src="/assets/images/lifestyle/RawDistCorr.png" class="img-fluid" style="max-height: 100%; width: 100%;" alt="RawData">
    </div>
  </div>
</div>
### <u> Overview </u>
<div class="container-fluid p-0 m-0 mb-4">
The distributions of Study, Extracurricular, and Sleep variables are generally uniform in shape, indicating consistent behavior across the sample. Social hours exhibit a nearly uniform distribution as well, with a slight skew towards higher social engagement. Physical activity, on the other hand, shows a pronounced right skew but does not fit well with common parametric distributions such as lognormal or gamma. Grades, contrastingly, approximate a normal distribution, reflecting a balanced spread around the mean.<br><br>
	
Correlation analysis reveals mostly weak or negligible relationships among these factors, with two notable exceptions: physical activity and studying. Physical activity shows weak correlations with all other variables, suggesting that increased time spent on exercise may come at the expense of other pursuits. Unsurprisingly, the strongest observed association is between studying and grades, highlighting that greater study time is linked with higher academic performance. <br><br>

To provide a clearer picture of how these variables distribute across different levels, I grouped each factor into three categories, low, medium, and high, by dividing their range (maximum minus minimum) into three equal intervals. This simple categorization allows for easy visualization and interpretation. The following pie charts illustrate the proportion of students falling into each level for the respective factors, offering an accessible overview of the data’s structure before deeper analysis.
</div>

<div class="border rounded p-2" style="max-height: 100%; width: 100%; display: inline-block;">
  <img src="/assets/images/lifestyle/FractionPies.png" class="img-fluid" style="max-height: 100%; width: 100%;" alt="RawData">
</div>

<div class="container my-4 mb-4">
  <div class="row align-items-center">
    <!-- Left Column: Text -->
    <div class="col-md-6 text-center">
      <h2 class="display-5 fw-bold text-black" style="text-shadow: 1px 1px 2px rgba(0,0,0,0.2);">
        Most of the students reported<br>a high level of stress
      </h2>
    </div>

    <!-- Right Column: Image -->
    <div class="col-md-6 d-flex align-items-center justify-content-center mb-4">
      <img src="/assets/images/lifestyle/FractionStressPie.png"  alt="StressPie" style="max-height: 100%; width: 100%;">
    </div>
  </div>
</div>
<br>
## Data Analysis
<div class="container-fluid p-0 m-0 mb-4">
Next, I investigate the relationship between each activity-related factor and student stress levels, aiming to address the question: Does increased engagement in various activities contribute to higher or lower stress? To explore this, the data for each activity, such as studying, sleeping, socializing, and exercising, was binned according to students' reported stress levels. This binning process allowed for a direct comparison of activity patterns across low, moderate, and high stress groups. To assess whether the differences observed between stress levels were statistically meaningful, I conducted a permutation test with 1,000 iterations for each factor. This non-parametric approach provides a robust evaluation of whether any apparent trends are likely due to chance or reflect a true underlying relationship between activity levels and student stress.
</div>

<div class="container my-4 mb-4">
  <div class="row align-items-center">
    <!-- Left Column: Text -->
    <!-- Right Column: Image -->
    <div class="col-md-7 d-flex align-items-center justify-content-center mb-4">
      <img src="/assets/images/lifestyle/SigStress_Activity.png" alt="StressPie" style="max-height: 100%; width: 100%;">
    </div>
    
        <div class="col-md-5 text-center">
	<h4 class="fw-bold" style="font-size: 2.5rem; color: #0047AB; text-shadow: 1px 1px 2px rgba(0,0,0,0.2);">
        More Studying and Higher GPA With High Stress <br><br>
        More Sleep and Physical Activity With Low Stress <br><br>
        Extracurricular and Social Have Little Impact on Stress
      </h4>
    </div>
  </div>
</div>



