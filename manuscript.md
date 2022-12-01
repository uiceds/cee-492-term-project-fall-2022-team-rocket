---
title: Predicting Delamination in Concrete Bridge Decks from Ground Penetrating Radar Signals using Machine Learning
keywords:
- markdown
- publishing
- manubot
lang: en-US
date-meta: '2022-12-01'
author-meta:
- Ishfaq Aziz
- Jesus Castro
- Chirayu Kothari
- Omar Abdelrahman
header-includes: |-
  <!--
  Manubot generated metadata rendered from header-includes-template.html.
  Suggest improvements at https://github.com/manubot/manubot/blob/main/manubot/process/header-includes-template.html
  -->
  <meta name="dc.format" content="text/html" />
  <meta name="dc.title" content="Predicting Delamination in Concrete Bridge Decks from Ground Penetrating Radar Signals using Machine Learning" />
  <meta name="citation_title" content="Predicting Delamination in Concrete Bridge Decks from Ground Penetrating Radar Signals using Machine Learning" />
  <meta property="og:title" content="Predicting Delamination in Concrete Bridge Decks from Ground Penetrating Radar Signals using Machine Learning" />
  <meta property="twitter:title" content="Predicting Delamination in Concrete Bridge Decks from Ground Penetrating Radar Signals using Machine Learning" />
  <meta name="dc.date" content="2022-12-01" />
  <meta name="citation_publication_date" content="2022-12-01" />
  <meta name="dc.language" content="en-US" />
  <meta name="citation_language" content="en-US" />
  <meta name="dc.relation.ispartof" content="Manubot" />
  <meta name="dc.publisher" content="Manubot" />
  <meta name="citation_journal_title" content="Manubot" />
  <meta name="citation_technical_report_institution" content="Manubot" />
  <meta name="citation_author" content="Ishfaq Aziz" />
  <meta name="citation_author_orcid" content="0000-0001-5723-0331" />
  <meta name="citation_author" content="Jesus Castro" />
  <meta name="citation_author_orcid" content="0000-0002-7684-7422" />
  <meta name="citation_author" content="Chirayu Kothari" />
  <meta name="citation_author_orcid" content="0000-0003-4468-1138" />
  <meta name="citation_author" content="Omar Abdelrahman" />
  <meta name="citation_author_orcid" content="0000-0003-0618-8481" />
  <link rel="canonical" href="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/" />
  <meta property="og:url" content="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/" />
  <meta property="twitter:url" content="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/" />
  <meta name="citation_fulltext_html_url" content="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/" />
  <meta name="citation_pdf_url" content="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/manuscript.pdf" />
  <link rel="alternate" type="application/pdf" href="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/manuscript.pdf" />
  <link rel="alternate" type="text/html" href="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/v/656f717c6c09b92c30e2c652bd30a76f50601a97/" />
  <meta name="manubot_html_url_versioned" content="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/v/656f717c6c09b92c30e2c652bd30a76f50601a97/" />
  <meta name="manubot_pdf_url_versioned" content="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/v/656f717c6c09b92c30e2c652bd30a76f50601a97/manuscript.pdf" />
  <meta property="og:type" content="article" />
  <meta property="twitter:card" content="summary_large_image" />
  <link rel="icon" type="image/png" sizes="192x192" href="https://manubot.org/favicon-192x192.png" />
  <link rel="mask-icon" href="https://manubot.org/safari-pinned-tab.svg" color="#ad1457" />
  <meta name="theme-color" content="#ad1457" />
  <!-- end Manubot generated metadata -->
bibliography:
- content/manual-references.json
manubot-output-bibliography: output/references.json
manubot-output-citekeys: output/citations.tsv
manubot-requests-cache-path: ci/cache/requests-cache
manubot-clear-requests-cache: false
...






## Authors



+ **Ishfaq Aziz**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [0000-0001-5723-0331](https://orcid.org/0000-0001-5723-0331)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [ishfaqa2](https://github.com/ishfaqa2)<br>
  <small>
  </small>

+ **Jesus Castro**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [0000-0002-7684-7422](https://orcid.org/0000-0002-7684-7422)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [jcastr54](https://github.com/jcastr54)<br>
  <small>
  </small>

+ **Chirayu Kothari**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [0000-0003-4468-1138](https://orcid.org/0000-0003-4468-1138)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [ck0103](https://github.com/ck0103)<br>
  <small>
  </small>

+ **Omar Abdelrahman**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [0000-0003-0618-8481](https://orcid.org/0000-0003-0618-8481)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [oaa4](https://github.com/oaa4)<br>
  <small>
  </small>



## Introduction {.page_break_before}


<div style="text-align: justify">Visual inspection of structures provides valuable information for QC/QA purposes, but its value is proportional to the knowledge and experience of the inspector. Still, visual inspections are limited to the features visible on accessible surfaces. Exploratory investigations (by destructive methods) have been conducted to ensure the internal conditions of structural elements under the assumption that the obtained results represent the conditions of an entire section (or region) in the structure. Then, the need for nondestructive methods arises. Nondestructive methods allow the evaluation of internal conditions without affecting the surface conditions. These methods usually rely on the acoustics and electrical properties of the materials.</div>

<div style="text-align: justify">Ground Penetrating radar (GPR) is a nondestructive method that relies on the dielectric properties of materials and can be used (in civil engineering practices) to locate steel and internal defects in concrete pavements. GPR is an effective tool for subsurface inspection and quality control on engineering construction projects. The survey method is rapid, nondestructive, and noninvasive. Interpretation of GPR data commonly helps to evaluate and measure different properties of a concrete structure.
</div>

<div style="text-align: justify">The data collected from the GPR are usually presented in two different formats, A-scan, and B-scan. Most modern devices can present both formats simultaneously. The A-scan is the raw energy signal received by the antenna shown as a function of time and signal strength (amplitude). The received signal in Figure 1a is an example of an A-scan. The B-scan, also known as radargram, is constructed from the sequence of multiple A-scans related to the antenna's position, as shown in Figure 1b, where the depth is represented on the y-axis, and the survey distance is shown on the x-axis orthogonal to the y-axis. The amplitude of the received signal is often shown as a color-coded intensity plot, often in grey, as shown in Figure 1c. B-scans are usually visually inspected to identify and locate any delamination within the concrete or to locate the reinforcement rebars.</div>

![
**a) Single wave signal (A-scan). b) Collection of signals across a distance along the surface. c) Color intensity plot of (b) (B-scan). [2]**
](https://user-images.githubusercontent.com/112973477/191904010-0450a119-488a-4a82-87aa-05a5d74f23d9.png "Wide image"){#fig:wide-image}

<div style="text-align: justify">Usually, the GPR is used to detect delamination defects in the pavements. Delamination defects can be under or over the rebars. It is very difficult to observe the defects which are under the rebars. Here, we analyzed a GPR data set that was prelabelled for three classes containing no defects and delamination over the rebars and under the rebars. Models like decision tree, random forest, regression, and convolutional neural networks were used to predict the classes based on the A-scans. The input of the model was either the raw scans, principal components, or the dominant frequency and amplitude in the FFT domain. </div>

## Description of Dataset {.page_break_before}
<div style="text-align: justify">The data was obtained from https://commons.und.edu/data/19/ [1], which contains annotated dataset for the structural defects. Data is present in the. xlsx format. Each column in the dataset has an approximate length of 512, where the first column represents the time (ns), and the rest of the columns are all amplitudes of GPR signals. Hence, each raw signal (columns) is directly annotated to one of the three possible classes. In addition, other information like the scan length and the coordinates of each signal scan is also provided. </div>

<div style="text-align: justify">The data set represents raw signals of Non-Destructive Evaluation (NDE) tests conducted by Ground Penetrating Radar (GPR) which were collected from in-service reinforced concrete bridge decks. The dataset was annotated using three classes by bridge deck repair: Class 1-No Delamination, Class 2-Delamination (delamination above top bar mat), and Class 3-Delamination (delamination below top bar mat). </div>





## Exploratory Data Analysis {.page_break_before}

### Preliminary Analysis


<div style="text-align: justify">The dataset consists of 16,384 GPR scans taken at different locations along the bridge. Each scan has a total of 512 points representing a scan time of 12 ns. The scans are categorized into class 1 – no delamination, class 2 – delamination above the top rebar, and class 3 – delamination below the top rebar, representing 8427, 6812, and 1144 scans, respectively, as shown in Table 1. Other properties of the GPR scans are summarized in Table 2. </div>


<div style="text-align: center">**Table 1. Summary of classes/labels of the dataset**</div>
| Classes | Class 1 | Class 2 | Class 3 |
|:-----------------|:-------------:|:-------------:|:-------------:|
| No of scans | 8427 | 6812 | 1144 |
| Meaning of each class | Sound Concrete | Concrete with delamination above top rebar | Concrete with delamination below top rebar |
| Peak amplitude of mean signal | 10121 | 9813 | 9649 |


<div style="text-align: center">**Table 2. Properties of the GPR scans**</div>
| Parameter | Value |
|:-----------------|:-------------:|
| Total number of scans | 16,383 |
| Total Length of scan | 363.3 ft. |
| Interval between subsequent scans | 0.0222 ft. |
| Time duration of each scan | 12 nano seconds |
| Data points per scan | 512 |
| Sample rate (calculated) | 42.67 GHz |


<div style="text-align: justify">The amplitudes of the signals in the dataset were found to have high numerical values. The average amplitude of the whole dataset is around 33,000. So, to make the data more symmetric around the x-axis, the average of the first few nanoseconds of readings was subtracted from the whole dataset, resulting in scans that start with amplitudes close to zero. Figure 2 shows one randomly selected scan from each of the three classes. </div>

![
**Randomly selected signals from each of the three classes**
](https://user-images.githubusercontent.com/112973477/198888009-6b6bffa6-3a3a-412d-8b55-2a129d1115b6.png "Tall image"){#fig:tall-image height=2in}


<div style="text-align: justify">Based on the reference paper used to obtain the data [1], the B-scan, a visual representation of a combination of individual scans stitched together, showed that the bottom rebar reflection was detected at around 7 ns. Thus, it was decided that the readings after around 8-ns would not be useful for our model, and the remaining 4 ns were removed. Also, it was observed that the initial reflection from the top surface of the concrete is detected around 2 ns, so the first 2 ns were also removed from our data. Sample scans from the resulting signal are shown in Figure 3.</div>


![
**Randomly selected signals from each class, showing only the data points between 2 and 8 ns.**
](https://user-images.githubusercontent.com/112973477/198888092-eba56164-5253-424a-b1bf-66a6aad0e06d.png
 "Tall image"){#fig:tall-image height=2in}



### Mean Plots
<div style="text-align: justify">To visually distinguish between the three different classes of data, the mean of all scans from each class is plotted in Figure 4. The figure shows that the three means look almost identical, so there is no distinctive feature in the time domain signal that can help assign new signals to any of the three classes. Thus, deeper levels of data analysis are required to identify any distinctive features that can help classify new data.</div>

![
**The mean of all signals for each class.**
](https://user-images.githubusercontent.com/112973477/198890014-03682ba5-2c91-4b70-a74a-ad6100371880.png
 "Tall image"){#fig:tall-image height=2in}






### Fast Fourier Transform (FFT)

<div style="text-align: justify">Another approach to visualizing sinusoidal time-series datasets is by identifying dominant cyclic patterns. This can be conducted with the Fast-Fourier Transform, a computationally efficient way to calculate the discrete Fourier Transform from a dataset. This algorithm transforms information on the time domain into the frequency domain. </div>

<div style="text-align: justify">The time-series datasets from the three classes (no delamination, delamination above rebar, and delamination below rebar) were all transformed into the frequency domain to identify patterns that could easily differentiate one class from another.  As observed in Figure 5, most of the signal amplitude peaks are observed at a frequency of approximately 0.8 GHz, which is in the standard operating frequency range of GPR antennas for concrete testing. </div>




![
**Amplitude vs Frequency Class 1 with no delamination**
](https://user-images.githubusercontent.com/112973477/198796951-76d47c3a-a1fd-4806-930c-1861941641d2.png "Tall image"){#fig:tall-image height=2in}

<div style="text-align: justify">In Figure 6, it is observed that in the sections where delamination was identified above the top rebar layer, the amplitude peaks were higher in magnitude than the observed peaks in the areas with non-delaminated sections at similar frequencies. On the other hand, the plot corresponding to the amplitudes of sections identified with delamination below the top rebar later (Figure 7.) displays amplitude peaks with magnitudes lower than in Figure 5 and Figure 6.</div>

![
**Amplitude vs Frequency Class 2 with delamination above the rebar**
](https://user-images.githubusercontent.com/112973477/198805626-7db1d0f0-c922-4421-bd7a-98ac69ab4543.png "Tall image"){#fig:tall-image height=2in}


![
**Amplitude vs Frequency Class 3 with delamination below the top rebar**
](https://user-images.githubusercontent.com/112973477/198806202-022ebb9c-4fc1-48c4-ba29-be7df7647d4f.png "Tall image"){#fig:tall-image height=2in}

<div style="text-align: justify">From this data processing approach (FFT), a good differentiation from the three classes (beyond the observed magnitudes in amplitude at approximately 0.8 GHz) cannot be concluded. Furthermore, the maximum amplitude of the FFT data and the frequency corresponding to the maximum amplitude was plotted (Figure 8). It was observed that the maximum amplitude of most of Class 1 and Class 2 was similar. However, some of the FFT spectra in Class 2 had higher amplitude than that of Class 1. Also, some of the FFT spectra in Class 2 had amplitude close to the mean of Class 3. It can be attributed to the labeling of data. </div>


![
**Violin plots representing the variation in maximum FFT amplitude of the three classes.**
](https://user-images.githubusercontent.com/112973477/198889209-6eba3151-f991-4375-9624-e01f7215b095.png
 "Tall image"){#fig:tall-image height=2in}


<div style="text-align: justify">Similarly, the frequency at maximum amplitude was observed for the FFT spectra in the three classes (Figure 9). The mean frequency at maximum amplitude for class 3 was lower than that of class 2 and class 1. The Violin plot for class 1 and class 2 look similar. However, some of the FFT spectra in class 2 have a frequency at a maximum amplitude lower than that of class 1’s data. </div>

![
**Violin plot representing the variation in frequency at maximum FFT amplitude of the three classes.**
](https://user-images.githubusercontent.com/112973477/198889398-21f6da40-2975-4964-b01e-6223ac78a1ce.png
 "Tall image"){#fig:tall-image height=2in}


<div style="text-align: justify">It can be easier to separate Class 3 from Class 1 and Class 2 based on the FFT analysis. </div>



### Principal Component Analysis
<div style="text-align: justify">Principal component analysis (PCA) was performed on the dataset to change the basis of the data and improve its interpretability. The number of modes was selected to be 2. The results of the first and second modes of the PCA data of the whole dataset are plotted in Figure 10. Since the number of data points for each class is different, normalizing the number of points might provide a better visual representation of the scattering of data in different classes. So, 1000 random points were selected from each class, and then PCA was performed on this sub-dataset. The results of the two modes of this PCA are shown in Figure 11. </div>

![
**The PCA data for all the datasets.**
](https://user-images.githubusercontent.com/112973615/198893083-66b632bb-c221-4a99-9b82-824d0ea6b08f.png "Tall image"){#fig:tall-image height=2in}




![
**PCA data of two different 1000 randomly selected points from each class.**
](https://user-images.githubusercontent.com/112973477/198889098-bd49b954-add9-4b08-bf6d-740e00b753ae.png "Tall image"){#fig:tall-image height=2in}


## Predictive Modeling {.page_break_before}

<div style="text-align: justify">Based on the exploratory data analysis, it can be concluded that the differentiation of the classes is challenging. The analytical approach to determining key features for distinguishing different classes is not conclusive, and overall, the data delineation is not observed. Hence, four different types of models, including the Convolutional Neural Network (CNN), were used to classify the delamination into three categories. The dataset was divided into training and testing data. </div> 

<div style="text-align: justify">The four models used in the preliminary predictive modeling are ‘Decision Tree’, ‘Random Forest’, ‘Regression’, and ‘1-D Convolutional Neural Network’. These models’ explanations and the corresponding results are discussed below.  </div>

### 1. Decision Tree
<div style="text-align: justify">The first predictive model applied was the ‘Decision tree’ model, a non-parametric supervised learning method that can be used for classification or regression. Deeper trees lead to more complex decision rules and, therefore, better model fitting.  </div> 

<div style="text-align: justify">Decision tree in machine learning has the advantage of being simple to understand, interpret and visualize. The model can be visually represented by a flowchart of decisions. It can also implicitly perform variable screening or feature selection to determine the most dominant variables that can govern the classification more than the others. However, it also comes with some limitations. For instance, decision tree learners can create over-complex trees that do not generalize the data well, causing data overfitting. In addition, the predictions of decision trees are neither smooth nor continuous, so they do not perform well with extrapolation.</div> 

<div style="text-align: justify">The decision tree classifier was created using 3 labels -one for each class- and 12 variables. These variables are the 10 first PCA modes of the data, the dominant FFT frequency, and its corresponding amplitude. The first 10 PCA modes were selected as they cover more than 90% of the variance. Then, leaves having more than 90% combined purity were merged before applying the model to avoid overfitting. About 60 % of the data from each class was used for training the model. Then, the model was tested on the complete dataset.  </div> 

<div style="text-align: justify">The summary of the results is shown in Table 3. The accuracy achieved on training data for classes 1, 2, and 3 were around 86%, 83%, and 46%, respectively. This resulted in an overall accuracy of about 82% on the training data. Due to the lower number of Class 3 data points, the model prediction accuracy is lower for class 3 than for the other two classes. The confusion matrices achieved by using this model are shown in Figure 12. When applied to the complete dataset, the achieved accuracy was around 67%, which means that the accuracy of the unseen 40% of data was about 45%. </div> 

![
**Confusion matrix of the training data for the ‘Decision Tree’ model**
](https://user-images.githubusercontent.com/112973532/202886315-d628336a-e1a5-4879-831e-92af119b0257.png "Tall image"){#fig:tall-image height=2in}


### 2. Random Forest
<div style="text-align: justify">To avoid the problem of overfitting, we have also tried to apply the ‘Random Forest’ classifier. A random forest is a meta-estimator that fits several decision tree classifiers on various sub-samples of the dataset and uses averaging to improve the predictive accuracy and control over-fitting. The parameters used for building our model are listed below: </div>

•	Number of random features = 6

•	Trees = 10

•	Portions of samples per tree = 0.6

•	Maximum tree depth = 17

<div style="text-align: justify">The accuracy obtained by the model using the numbers mentioned above was around 64 %. Values of these parameters were changed to default values (default of the package: DecisionTree.jl), and then the new model was generated and tested. With the default values, the achieved accuracy was around 66 %.  </div> 


### 3. Regression
<div style="text-align: justify">Regression is a method for creating a model of the relationship between one or more independent variables and dependent variables, where variation in the dependent variables is used to explain variation in the dependent variables. The regression method prepared for this project considered a total of 260 independent variables and 1 dependent variable (classification). The regression model was optimized by minimizing a maximum square error function used a learning rate of 0.001 and 10,000 steps. 60% of the entire data set was used as training for the regression model.</div>

<div style="text-align: justify">Ideally, regression model results should match actual observations. As observed in Figure 13(a), similar values were predicted for the three observed classes, which enables this system alone to accurately classify the predictions. These findings, plus observations from the confusion matrix in Figure 13(b), confirm that the regression model is inadequate for a classification model.</div>

![
**(a) Class Predictions vs Actual Classes, from regresion-based machine learning model. (b)Confusion matrix for the regression-based model**
](https://user-images.githubusercontent.com/112973477/205181215-1af2882f-8278-46cc-84db-4a39f64a9e0a.png "Tall image"){#fig:tall-image height=2in}


### 4. Convolutional Neural Network
<div style="text-align: justify">The Convolutional Neural Network (CNN) was created for the GPR data at different locations. Out of the approximately 16000 signals, around 9800 random signals were used to train the model. Each signal has 260 data points. The 1D CNN is composed of several layers. The first layer was a convolution layer with a filter size = 5 with 1 input channel to 8 output channels of training data. The padding was of size= 2 and Relu was the activation function. The next layer was a Maxpool layer of size= 4. The third layer is another convolutional layer with a filter of a size = 5 and padding of size= 2 with 8 channels to 3 channels. The fourth layer with a Maxpool layer of size =5 and the fifth layer is a dense layer of size (39,3) based on the input size and the number of channels. Finally, a Softmax layer is applied to discriminate between different classes. The batch size was 10 and learning rate was 0.001.</div>

<div style="text-align: justify">Figure 14 show some diagnostics of our model training, include loss and accuracy curves as a function of gradient descent step and a confusion matrix of the final results. The accuracy of 52% is achieved based on the convolutional neural network. As observed in the figure , the accuracy becomes constant after certain epochs and does not improve. The model was further executed for different channels as well as different activation functions like Relu, Tanh, and its combination. However, the output was close to 52% accuracy with no improvement. The rest 40% of the total data was tested based on the CNN model. The accuracy was again 52% and the correlation matrix for the testing data was similar to that of the correlation matrix for the training data(scales on the color bar are different as the number of datasets for training and testing data is different). Further modification and improvements in the CNN model are required.</div>

![
**Performance of the CNN model. It shows the loss and accuracy curves as a function of gradient descent step and a confusion matrix for both the training data and the testing data**
](https://user-images.githubusercontent.com/112449929/205139444-7675a88c-fd70-4d88-b84c-4310f9156efc.png "Tall image"){#fig:tall-image height=4in}


### Discussions
<div style="text-align: justify">As mentioned, the data is classified into three (3) different labels/classes. However, the amount of data samples for the three classes is not the same. For example, class 3 represents only about 7.5% of the entire dataset, while class 1 is approximately 50%. 
Table 3 provides a accuracy/performance based summary of the effectiveness of each of the studied predicitve models.The accuracy of predictive models is linked to the sample size of each class. An imbalanced dataset may cause predictive models to be biased towards learning more about the dominant classes causing higher accuracy of prediction of these classes. Moreover further improvement in CNN model by optimizing the model parameters and layers is required. Regresion model showed the lowest accuracy from the predictiv Decision Tree and Random Forest models provided relatively high accuracy levels on training data (above 75%), 1-D CNN model provided the highest accuracy on unseen data with 52%.</div>


<div style="text-align: center">**Table 3. Summary of results of predictive modeling**</div>
| Models | Training data | Accuracy On Training data | Accuracy On Unseen data |
|:-------------|:-------------:|:-------------:|:-------------:|
| Decision Tree | 60 % | 82 % | 45 % |
| Random Forest | 60 % | 76 % | 49 % |
| Regression | 60 % | 33 % | 34 % |
| 1-D CNN |	60% | 52 % |52 % |		

## References 

[1] Ichi, E., & Dorafshan, S. (2021). SDNET2021: Annotated NDE Dataset for Structural Defects, 10.31356/data019

[2] Scheers, B., 2001. Chapter 2. Ground penetrating radar. In: Ultra-Wideband Ground Penetrating Radar, with Application to the Detection of Anti-Personnel Landmines. Brussels: s.n., pp. 2-1 -2-43.

<div id="refs"></div>
