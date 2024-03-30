# harshald007-Combining-Machine-Learning-and-Rules-forCybersecurity

### The Art and Science of Cybersecurity Attack Detection: A Hybrid Approach


This project aims to improve cyber security by developing a machine learning and rule-based approach to detect cyber attacks. The approach involves analyzing network data to identify potential attacks by identifying correlations between various variables. By completing this project, you will be able to understand how to analyze network data and identify the variables associated with cyber attacks. By leveraging machine learning algorithms and rule-based approaches, this project helps to improve the accuracy and efficiency of cyber attack detection, thereby enhancing the security of digital networks and systems. This project is a valuable first step towards becoming a cyber security expert.

| <img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-GPXX0Q8REN/CC_CybersecurityDetection.png" width="600" alt="Cyber attack image"> |
|:--:| 

## __Table of Contents__

<ol>
    <li><a href="#Objectives">Objectives</a></li>
    <li>
        <a href="#Setup">Setup</a>
        <ol>
            <li><a href="#Installing-Required-Libraries">Installing Required Libraries</a></li>
            <li><a href="#Importing-Required-Libraries">Importing Required Libraries</a></li>
        </ol>
    </li>
    <li><a href="#3.-Strategies-to-Detect-Cyber-Attacks">Strategies to Detect Cyber Attacks</a></li>
    <li>
        <a href="#4.Cyber Attack Data">Cyber Attacks Data</a>
        <ol>
            <li><a href="#Data Exploration">Data Exploration</a></li>
        </ol>
    </li>
    <li>
        <a href="#5.Rule-Based System">Rule-Based System</a>
        <ol>
            <li><a href="#Evaluation Metric">Evaluation Metric</a></li>
            <li><a href="#Introducing Snort">Introducing Snort For Rule-Based System</a></li>
        </ol>
    </li>
     <li>
        <a href="#6.Machine Learning Model For Cyber Attack Detection">Machine Learning Model For Cyber Attack Detection</a>
        <ol>
            <li><a href="#Building a RandomForest Model">Building a RandomForest Model</a></li>
        </ol>
    </li>
    <li>
        <a href="#7.Human Analysis">Human Analysis</a>
        <ol>
            <li><a href="#7.1. Correlations In The Dataset">Correlations In The Dataset</a></li>
            <li><a href="#7.2 Feature Ranking From Random Forest">Feature Ranking From Random Forest</a></li>
            <li><a href="#7.3 Discussing The Network Features">Discussing The Network Features</a></li>
        </ol>
    </li>
     <li>
        <a href="#8.Cyber Security for Cloud Services">Cyber Security for Cloud Services</a>
    </li>
     <li>
        <a href="#9.List of All Features With Descriptions">List of All Features With Descriptions</a>
    </li>
</ol>


##  1.Objectives

Our main goal is to understand how attacks happen and what are the important indicators of attack. by knowing that, we can implement a monitoring system for attack detection. By completing this project, you will be able to apply your learnings to real-world scenarios and contribute to the ongoing effort to secure the cyber realm.

After completing this lab you will be able to:

- Understand how cyber attacks occur and identify important indicators of attacks.
- Implement a monitoring system for attack detection using both rule-based and machine learning approaches.
- Learn how to visualize variables in network data.
- Gain experience in using machine learning algorithms such as Random Forest for classification and feature ranking.
- Enhance your knowledge and skills in cybersecurity and introducing powerful tools to equipped to detect and prevent cyber attacks.

## 2. Setup
### 2.1 Installing Required Libraries

The following required libraries are pre-installed in the Skills Network Labs environment. However, if you run this notebook commands in a different Jupyter environment (e.g. Watson Studio or Ananconda), you will need to install these libraries in the code cell below.

%%capture 
!pip install -U 'skillsnetwork' 'seaborn' 'nbformat' 

%%capture 
!pip install scikit-learn==1.0.0
!pip install dtreeviz

>  _YOU NEED TO <span style="color:red"> **RESTART THE KERNEL** </span> by going to the `Kernel` menu and clicking on `Restart Kernel`._ 

### 2.2 Importing Required Libraries

_import some essential libraries_

# You can also use this section to suppress warnings generated by your code:
def warn(*args, **kwargs):
    pass
import warnings
warnings.warn = warn
warnings.filterwarnings('ignore')

#import shap
import skillsnetwork
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
%matplotlib inline

sns.set_context('notebook')
sns.set_style('white')




