<!-- TITLE & AUTHORS -->
<h1 align="center">Enhancing Pedestrian Safety in Great Britain</h1>
<h3 align="center">Analysis of Road Collision Data and Policy Effectiveness</h3>

<p align="center">
By Tian Tong | Instructor: Prof. Ioannis Ziogas  
</p>

<!-- ABSTRACT -->
<h2 id="abstract">Abstract</h2>

<p>
This project analyzes the conditions associated with serious or fatal pedestrian-involved road collisions in Great Britain using the 2023 Road Safety Data published by the UK Department for Transport.
</p>

<p>
Using machine learning techniques, we identify key environmental and infrastructural risk factors and assess the effectiveness of recent road safety policies, such as the 2022 Highway Code revision. The study combines predictive modeling and model interpretation to provide data-driven recommendations for improving pedestrian safety and informing future policy interventions.
</p>

<!-- METHODOLOGY -->
<h2 id="methodology-summary">Methodology</h2>

<p>
We built a supervised machine learning pipeline to model and interpret pedestrian-related collision outcomes using structured traffic data from the UK Department for Transport.
</p>

<ul>
  <li><strong>Targets:</strong>     <ul>
      <li>Whether a collision involved a pedestrian</li>
      <li>Whether the collision resulted in serious or fatal injuries</li>
      <li>Whether a pedestrian-involved collision was also serious or fatal</li>
    </ul>
  <li><strong>Models:</strong> Random Forest and XGBoost (with hyperparameter tuning)</li>
  <li><strong>Imbalance Handling:</strong> SMOTE used to improve classification of rare events</li>
  <li><strong>Evaluation:</strong> Accuracy, Precision, Recall, F1-Score, and ROC AUC</li>
  <li><strong>Interpretation:</strong> SHAP used to identify key contributing factors (e.g., speed limits, lighting, road conditions)</li>
</ul>

<p>
For detailed preprocessing and modeling steps, see: <a href="notebooks/Methodology.ipynb"><code>Methodology.ipynb</code></a>
</p>


<!-- OBJECTIVES -->
<h2 id="objectives">Objectives</h2>

<ul>
  <li><strong>Identify key risk factors</strong> associated with serious or fatal pedestrian-involved collisions</li>
  <li><strong>Predict accident severity</strong> and pedestrian involvement using real-world collision data</li>
  <li><strong>Model interaction outcomes</strong> to isolate high-risk incidents involving both pedestrians and severe injury</li>
  <li><strong>Interpret feature importance</strong> using SHAP to support transparent, data-driven decision-making</li>
  <li><strong>Generate policy recommendations</strong> to guide road safety improvements and enforcement strategies</li>
</ul>


<!-- DATASET -->
<h2 id="dataset">Dataset</h2>

<p>
This project is based on the <strong>2023 Road Safety Data</strong> published by the <strong>UK Department for Transport</strong>. The dataset originates from the STATS19 data collection system, which compiles all police-reported road traffic collisions involving personal injury across Great Britain.
</p>

<p>
Each record in the dataset represents a unique collision and includes detailed attributes such as the number of vehicles and casualties, road type, speed limit, weather and lighting conditions, junction characteristics, and whether a pedestrian was involved. The dataset includes both collision-level and casualty-level variables, which enables us to construct interaction terms to study the severity of pedestrian-involved incidents.

</p>

<p>
With over 49,000 records collected between January and December 2023, this dataset forms the foundation for our predictive modeling of pedestrian safety outcomes. It allows us to explore the structural and environmental conditions under which serious or fatal accidents are more likely to occur, and to evaluate how key features influence these risks.

  Specific definitions and explanations of variables are referenced from the official UK government documentation guidance on road accident and safety statistics, available <a href="https://www.gov.uk/guidance/road-accident-and-safety-statistics-guidance#quality-and-methodology">here</a>.

</p>

<ul>
  <li><strong>Data Source:</strong> <a href="https://www.data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-safety-data">STATS19 Road Safety Data 2023 (Collision-Level)</a></li>
  <li><strong>Size:</strong> ~49,000 police-reported collisions</li>
  <li><strong>Key Variables:</strong> number of vehicles, number of casualties, speed limits, road and weather conditions, lighting, pedestrian involvement, and junction details</li>
</ul>



<!-- PREREQUISITES -->
<h2 id="prerequisites">Prerequisites</h2>

<p>
This project is written in the Python programming language and requires the following libraries:<br>
<code>numpy</code>, <code>pandas</code>, <code>matplotlib</code>, <code>seaborn</code>, <code>scikit-learn</code>, <code>xgboost</code>, <code>shap</code>, <code>lime</code>, <code>imblearn</code>, <code>joblib</code>
</p>

<p>
These can be installed using <code>pip install</code> or your preferred environment manager (e.g., <code>conda</code>).
Additional dependencies such as <code>enable_iterative_imputer</code> are included in <code>scikit-learn</code>'s experimental features.
</p>

