<h1 align="center">
 Machine Learning (Classification & Linear Regression) for PEM Electrolyzer Hydrogen Production Prediction & Optimization
</h1>

<p align="center">
<b>ML Predictive Analytics for Accelerating Green Hydrogen Development</b>
</p>

<hr>


<h2> Project Overview</h2>

<p>
This project presents an end-to-end <b>Machine Learning framework for predicting and optimizing Proton Exchange Membrane (PEM) electrolyzer performance</b> by integrating <b>electrochemical engineering knowledge with modern data science methodologies.</b>
</p>

<hr>


<h2> Why PEM Electrolyzers?</h2>


<p>
Hydrogen is considered a critical energy carrier for achieving a low-carbon and sustainable energy future.
</p>


<p>
Among different hydrogen production technologies, 
<b>Proton Exchange Membrane (PEM) water electrolyzers</b> are highly promising because they provide:
</p>


<ul>
<li>High hydrogen purity</li>
<li>Fast dynamic response</li>
<li>Compact system design</li>
<li>Compatibility with renewable energy sources such as solar and wind</li>
<li>Potential for industrial-scale green hydrogen production</li>
</ul>


<h3>However, PEM Technology Faces Several Challenges</h3>


<h4>Material Challenges</h4>

<ul>
<li>High catalyst cost, especially platinum-group metals</li>
<li>Complex interaction between catalysts, membranes, and electrodes</li>
<li>Difficulty selecting optimal material combinations</li>
</ul>


<h4> Operational Challenges</h4>

<ul>
<li>Strong dependency on temperature, power, current density, and water flow</li>
<li>Performance variation under different operating conditions</li>
<li>Electrochemical degradation over time</li>
</ul>


<h4> Experimental Challenges</h4>

<p>
Traditional PEM optimization relies heavily on experimental trial-and-error approaches, which are:
</p>

<ul>
<li>Expensive</li>
<li>Time-consuming</li>
<li>Difficult to scale</li>
</ul>


<p>
The project addressed two main engineering challenges:
</p>

<li>Can hydrogen production be accurately predicted before performing additional experiments?</li>
<li>Can Machine Learning identify high-performance electrolyzer configurations based on materials and operating conditions?</li>
<li>The objective was to reduce experimental trial-and-error and support faster, data-driven PEM electrolyzer design decisions.</li>

<hr>

<h2> Problem Definition</h2>

<p>
An end-to-end Machine Learning framework was developed using experimental PEM electrolyzer data.
</p>

<h3>1. Hydrogen Production Prediction (Regression)</h3>

<p>
The model predicts:
</p>

<pre>
Hydrogen Flow Rate (mL/min)
</pre>

<p>
Using:
</p>

<ul>
<li>Current</li>
<li>Voltage</li>
<li>Power input</li>
<li>Temperature</li>
<li>Water flow rate</li>
<li>Catalyst properties</li>
<li>Electrode characteristics</li>
<li>Cell design parameters</li>
</ul>


<h3>2. Electrolyzer Performance Classification</h3>

<p>
Hydrogen production values were converted into performance categories:
</p>

<ul>
<li>Low Performance</li>
<li>Medium Performance</li>
<li>High Performance</li>
</ul>

<p>
The classification model learns:
</p>

<blockquote>
"What combination of materials and operating conditions leads to better electrolyzer performance?"
</blockquote>


<hr>


<h2> Dataset Understanding</h2>

<p>
The dataset contains experimental electrochemical measurements:
</p>

<ul>
<li><b>281 experimental samples</b></li>
<li><b>19 electrochemical and design variables</b></li>
<li>Numerical and categorical features</li>
</ul>


<h3>Feature Groups</h3>

<h4> Operational Variables</h4>
<ul>
<li>Cell current</li>
<li>Cell voltage</li>
<li>Power input</li>
<li>Temperature</li>
<li>Water flow rate</li>
</ul>


<h4> Material Variables</h4>

<ul>
<li>Anode catalyst</li>
<li>Cathode catalyst</li>
<li>Electrode material</li>
<li>Membrane type</li>
</ul>


<h4> Design Variables</h4>

<ul>
<li>Electrode area</li>
<li>Cell configuration</li>
</ul>


<h4>Target Variable</h4>

<ul>
<li>Hydrogen production rate</li>
</ul>
<hr>


<h2> Data Science Challenges & Solutions</h2>

<h3>Challenge 1: Experimental Data Quality</h3>

<p>
Raw laboratory data contained:
</p>

<ul>
<li>Missing values</li>
<li>Inconsistent chemical names</li>
<li>Mixed numerical and categorical variables</li>
<li>Different feature scales</li>
</ul>


<p><b>Example:</b></p>

<pre>
Before:

iridium_oxide_(iro2)
Iridium Oxide
IrO2


After:

IrO2
</pre>


<p>
<b>Solution:</b>
</p>

<ul>
<li>Missing value imputation</li>
<li>Chemical label standardization</li>
<li>Duplicate category removal</li>
<li>Feature scaling</li>
<li>Categorical encoding</li>
</ul>


<h3>Data Pipeline</h3>

<pre>

Raw Experimental Data

        ↓

Data Cleaning

        ↓

Feature Engineering

        ↓

Preprocessing Pipeline

        ↓

Machine Learning Models

</pre>


<hr>


<h2> Exploratory Data Analysis (EDA)</h2>

<p>
Before modeling, statistical analysis was performed to understand the physical behavior of PEM electrolyzers.
</p>


<h3>Hydrogen Production Distribution</h3>

<pre>
Skewness = +4.07
</pre>


<p>
The analysis showed:
</p>

<ul>
<li>Most experiments operate under moderate production conditions</li>
<li>A small number of optimized configurations achieve very high performance</li>
</ul>


<h3>Engineering Insights</h3>

<ul>
<li>Electrical input strongly influences hydrogen generation</li>
<li>Catalyst selection affects efficiency</li>
<li>Electrode materials influence stability</li>
<li>Temperature impacts reaction kinetics</li>
</ul>
<hr>


<h2> Machine Learning Model Development</h2>

<h3>Regression Models</h3>

<table border="1">

<tr>
<th>Model</th>
<th>Purpose</th>
</tr>

<tr>
<td>Linear Regression</td>
<td>Baseline relationship modeling</td>
</tr>

<tr>
<td>Ridge Regression</td>
<td>Handles correlated variables</td>
</tr>

<tr>
<td>Lasso Regression</td>
<td>Feature selection</td>
</tr>

<tr>
<td>Elastic Net</td>
<td>Robust prediction with regularization</td>
</tr>

<tr>
<td>Polynomial Regression</td>
<td>Nonlinear relationship modeling</td>
</tr>

<tr>
<td>SGD Regression</td>
<td>Optimization-based learning</td>
</tr>

</table>


<h3>Model Optimization</h3>

<ul>
<li>Train/Test Split</li>
<li>5-Fold Cross Validation</li>
<li>Hyperparameter Optimization</li>
<li>Residual Analysis</li>
<li>Generalization Testing</li>
</ul>


<hr>


<h2> Regression Result</h2>
<h3>Final Model: Elastic Net Regression</h3>

<pre>
Test R² = 0.9764
</pre>


<p>
Elastic Net was selected because PEM systems contain highly correlated variables:
</p>

<ul>
<li>Current</li>
<li>Voltage</li>
<li>Power</li>
<li>Operating conditions</li>
</ul>


<p>
The model achieved:
</p>

<ul>
<li>High prediction accuracy</li>
<li>Reduced overfitting</li>
<li>Stable feature interpretation</li>
</ul>


<hr>


<h2> Feature Importance Analysis</h2>

<p>
The model identified the most influential factors controlling hydrogen production.
</p>


<h3>1. Electrical Parameters</h3>

<ul>
<li><b>Cell Current:</b> strongest predictor because hydrogen generation follows Faraday's law.</li>
<li><b>Power and Voltage:</b> represent energy input and operational efficiency.</li>
</ul>


<h3>2. Material and Design Factors</h3>

<ul>
<li>Pt/C catalyst</li>
<li>IrO₂ catalyst</li>
<li>Titanium electrodes</li>
<li>Electrode area</li>
</ul>


<p>
These parameters influence reaction kinetics, overpotential, and system stability.
</p>


<hr>


<h2> Classification Framework</h2>

<p>
Regression predicts exact hydrogen production, but engineers also need rapid design screening.
</p>

<p>
Therefore, hydrogen production was converted into:
</p>

<ul>
<li>Low</li>
<li>Medium</li>
<li>High</li>
</ul>


<h3>Classification Models</h3>

<table border="1">

<tr>
<th>Model</th>
<th>Purpose</th>
</tr>

<tr>
<td>Logistic Regression</td>
<td>Interpretable baseline model</td>
</tr>

<tr>
<td>KNN</td>
<td>Similarity-based classification</td>
</tr>

<tr>
<td>Decision Tree</td>
<td>Nonlinear decision rules</td>
</tr>

<tr>
<td>AdaBoost</td>
<td>Ensemble learning improvement</td>
</tr>

</table>


<hr>


<h2> Classification Optimization</h2>

<ul>

<li>
<b>Logistic Regression:</b> optimized regularization strength and penalty type.
</li>

<li>
<b>KNN:</b> optimized number of neighbors and distance metric.
</li>

<li>
<b>Decision Tree:</b> optimized tree depth and minimum samples split.
</li>

<li>
<b>AdaBoost:</b> optimized number of estimators and learning rate.
</li>

</ul>


<h2> Classification Performance</h2>


<h3>Decision Tree Classifier</h3>

<pre>
Accuracy = 95%
</pre>


<ul>
<li>High-class Recall: 97%</li>
<li>High-class F1-score: 98%</li>
</ul>


<p>
The model successfully captured nonlinear relationships between catalyst selection, operating conditions, and electrolyzer configurations.
</p>


<h3>AdaBoost Classifier</h3>

<pre>
Accuracy = 88%
F1-score = 0.88
</pre>


<p>
AdaBoost improved learning by combining multiple weak learners to capture complex interactions.
</p>


<hr>


<h2> Final Impact</h2>

<p>
This project demonstrates how a Data Scientist can transform:
</p>

<pre>
Experimental Engineering Data
            ↓
Machine Learning
            ↓
Engineering Decisions
</pre>


<p>
The developed framework enables:
</p>

<ul>
<li>✅ Faster catalyst screening</li>
<li>✅ Reduced experimental trial-and-error</li>
<li>✅ Predictive hydrogen production modeling</li>
<li>✅ Data-driven electrolyzer optimization</li>
<li>✅ Accelerated green hydrogen development</li>
</ul>


<hr>


<h2> Technology Stack</h2>

<ul>
<li>Python</li>
<li>Pandas</li>
<li>NumPy</li>
<li>Scikit-learn</li>
<li>Matplotlib</li>
<li>Seaborn</li>
<li>Jupyter Notebook</li>
<li>Machine Learning</li>
<li>Statistical Modeling</li>
<li>Predictive Analytics</li>
</ul>


<hr>


<h2> Future Development</h2>

<ul>
<li>XGBoost and LightGBM optimization</li>
<li>Artificial Neural Networks</li>
<li>LSTM degradation prediction</li>
<li>Bayesian Optimization for autonomous experiments</li>
<li>Digital Twin development</li>
<li>Real-time AI optimization dashboard</li>
</ul>

