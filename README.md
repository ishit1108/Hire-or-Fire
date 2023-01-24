
# Introduction

<img width="627" alt="image" src="https://user-images.githubusercontent.com/76467751/214302229-bbdabc03-ea1c-4ca5-ae88-03aa8d8a313a.png">

# Installation

Download our repositiory .zip file or clone the directory using git commands. Extract the zipped file and directly run app.py file to create a localhost server to run the web application.

# Detailed Description About the Project

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 001](https://user-images.githubusercontent.com/76467751/214295716-a55f5d12-b804-4f9a-b3b6-2bc915504987.png)

Our project is a form of score predictor. Our project is a helping tool for hiring committees and HR department. It evaluates an employee over multiple factors. Our model is a culmination of four individual models. We run four different models, namely Attrition Classifier, Turnover Classifier, Absenteeism Classifier and Salary Predictor. We use different methods to calculate all four values. All individual values are graded out of ten while the overall score is graded out of 100.

<img width="623" alt="image" src="https://user-images.githubusercontent.com/76467751/214302784-f280bf6b-e7a6-49b8-a73f-f3b24ca5a21c.png">


We also perform abstraction as we only take the beta values of our models and use them to calculate scores on the GUI website. This makes the user interface light and easy to port and run. This also makes the backend independent. We can make updates to models without disturbing the running GUI.

We have made a comprehensive tool to judge the performance of an employee or a fresher. The employer just needs to enter a few details about the employee and after that our project takes over and gives us a score. The score may be used to decide whether to retain or fire an existing employee or in the case of freshers’ weather to hire them or not.

The following document is a detailed description of the working of our project along with info about the dataset and GUI working.

<img width="621" alt="image" src="https://user-images.githubusercontent.com/76467751/214303207-e84f87a9-0d74-4db4-9c7c-27f348789a8b.png">
<img width="623" alt="image" src="https://user-images.githubusercontent.com/76467751/214303331-f0eacd63-c0f1-47ec-9564-a53146f698cd.png">
<img width="622" alt="image" src="https://user-images.githubusercontent.com/76467751/214303520-f9c1a6c6-7967-4d5a-af51-ad8b5d70c403.png">
<img width="622" alt="image" src="https://user-images.githubusercontent.com/76467751/214303678-f40c4ee7-6d35-4b3c-8e71-3a56e0824eae.png">
<img width="620" alt="image" src="https://user-images.githubusercontent.com/76467751/214303789-039dcbea-d054-4698-b61d-4327d4b29e7e.png">
<img width="623" alt="image" src="https://user-images.githubusercontent.com/76467751/214303857-6be3dde8-1fbe-440f-84c5-c505e20d20fa.png">


Technology Used – Pre-processing

This project explores and utilizes a plethora of pre-processing tools and techniques to pipeline and ready the data to be fed into the machine learning model and neural network used in the project. Following is a list of the pre-processing tools used along with the purpose it serves in pipelining the data:

1. Label Encoding: 

Label encoding is one of the most essential steps of pre-processing. Our model is build using basic mathematical tools available in python, but even otherwise all models are build using mathematical tools; however, input data may also be in the form of strings and hence label encoding helps us to map **strings to integer values.** 

Alternative to label encoding is **mapping**. We can manually map strings to their respective integer values. But label encoding provides an easy way to encode literals to integers and hence we have used Label encoding.

Label encoding works by first finding all the unique values of the column passed. It then compares the values **lexicographically**, arranges it in ascending order and assigns numbers from 0 onwards. Following are a few screenshots of where we have used Label encoding:

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 002](https://user-images.githubusercontent.com/76467751/214296222-cea91469-ecac-4497-a516-aa6d47db1ef4.png)

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 003](https://user-images.githubusercontent.com/76467751/214296277-137fe96f-0c8f-4700-b2f4-f69d863cde7f.png)







1. Missingno:

Missingno is a package used to **find missing values** or **null values**. We have used the **bar** function to **plot** the values of all our features. From the bar plot it was evident that we did not have any missing or null values and hence we did not have to handle them.

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 004](https://user-images.githubusercontent.com/76467751/214296312-a9e6de26-0121-4bea-ab74-9e22f35952d5.png)


1. Countplot:

Present in the **seaborn package**, we used countplot to plot the count of occurrences of **unique values** of a feature. We have used it to view **class balancing**. At times when classification classes had uneven datasets, we have applied yet another pre-processing technique called **SMOTE** to balance the datasets as discussed later.

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 005](https://user-images.githubusercontent.com/76467751/214296357-85d05b48-5dc6-411f-92d9-88376aaaf45c.png)![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 006](https://user-images.githubusercontent.com/76467751/214296450-d5e29636-e40d-4a9b-992d-abac859e5ed3.png)






1. Heatmap (of correlation):

Present in the **seaborn package**, heatmap presents a comprehensive understanding of data. We used the heatmap to plot the **correlation of independent features**. Features having higher correlation were dropped from the dataset itself. We could have dropped those features from the python code also, but that would have hindered the code from executing more than once on a few platforms and IDEs. A correlation heatmap looks like the following:

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 007](https://user-images.githubusercontent.com/76467751/214298492-18a75689-a0ce-44e1-bd43-13f9a5d5b44a.png)

1. SMOTE (Synthetic Minority Oversampling Technique):

**SMOTE** is a technique to **balance classes** in **classification problems**. We could have balanced classed by simply reducing the number of majority samples but that could lead to **under sampling**. We could also have just duplicated the minority samples but that reduces the efficiency and often leads to **overfitting**. 

Hence, we used SMOTE. This method **synthetically generates** samples of the minority class. What it means is that, it creates a **random point** (random input variables), performs **K Nearest Neighbour (KNN) algorithm** and sees in which class does this random point belong. If the random point belongs to the minority class, then it adds that point to the sample. If the random point belongs to the majority class, then it simply discards the random point and takes another random point. This method keeps on taking random points until and unless both classes have become **balanced**. 

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 008](https://user-images.githubusercontent.com/76467751/214298512-79c6b2e8-0139-41c4-b30a-3d14ca682a5c.png)



`		`**Before SMOTE**			      **After SMOTE**

![](Aspose.Words.0c5aa5b8-8363-4085-bc25-097709bdd400.005.png)![](Aspose.Words.0c5aa5b8-8363-4085-bc25-097709bdd400.006.png)

1. Standard Scalar:

This pre-processing technique is used to **standardize** the input elements.  

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 009](https://user-images.githubusercontent.com/76467751/214298540-f365a8a5-bc72-4eaf-bc59-8b7e66b15c4f.png)

1. Outlier Removal:

This function is made to **remove outliers** from the data using the quantile function to retain data of a particular **inter-quartile range**.

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 010](https://user-images.githubusercontent.com/76467751/214298582-fabb5f18-7579-4980-89a4-61fa4c87fb2f.png)



Technology Used – Model Training

While most of the project is **developed base-up from scratch** using **basic python libraries** such as **NumPy** and **Pandas**, there are a few areas in which we employed other frameworks such as **TensorFlow** and **Keras** to implement advanced neural networks. Details of the technology used to develop models of individual components are as follows:

1. Salary: 

Salary being a continuous integer output requires regression. Normal multiple regression of various degrees yielded unsatisfactory results and hence we resolved to use neural networks. We developed a **Dense convolutional neural network**. The layers of the network are summarised in the diagram below:

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 011](https://user-images.githubusercontent.com/76467751/214298604-bdfbe794-a767-489f-b227-18b8f369356b.png)














Number of nodes in the diagram have been scaled down. In the actual network, the layers from first to last output consists of **256, 128, 64, 32 and 1 node** respectively. Each node has a **‘uniform’ kernel initializer** and **‘relu’ activation** while the last output Layer node has a **‘linear’ activation**.

After each layer there is a **dropout of 5%** to manage the edges of the network. The final compilation of the network is done through **‘adam’ optimizer** and **‘mean squared error’** **loss metric**. The network is formed with **dense** **connections** as can be seen from the diagram above.

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 012](https://user-images.githubusercontent.com/76467751/214298624-ef70e5fe-a4ea-4186-9ff5-bc57262ea695.png)

1. Attrition: 

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 013](https://user-images.githubusercontent.com/76467751/214298662-76663b96-0147-4d8c-91c7-3c53d468978a.png)As the output is binary in nature, hence **Logistic Regression** was employed. Many activation formulas were tested for most optimal output. The highest test accuracy was achieved by the **Activation Formula:**

y=11+e-z

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 014](https://user-images.githubusercontent.com/76467751/214298684-0166c45e-ce57-4399-b715-4a6ad5215c25.png)Where,

z=β0+β1x1+β2x2+⋯+βnxn

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 015](https://user-images.githubusercontent.com/76467751/214298704-aa115087-064d-4055-96a2-525657d40700.png)

1. Absenteeism:

As absenteeism represents the number of leaves an employee takes, the output can neither be considered continuous nor binary. Hence, we divided the output into different classes making this a multiclass classification problem. We used the same **Logistic Regression** with the same activation formula as above. However, we had to **create dummies** of the output feature effectively giving us 4 output features for the four different classes.

**Activation Formula:** y=11+e-z

Where, z=β0+β1x1+β2x2+⋯+βnxn

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 016](https://user-images.githubusercontent.com/76467751/214298750-d0a51c78-4717-47ad-b9ae-7958d7beeb68.png)![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 017](https://user-images.githubusercontent.com/76467751/214298818-622c1a5d-42b1-46fd-95d8-3b288f8f9d85.png)

1. Turnover:

The turnover dataset has a binary output; however, the relation was found out to be non-linear. To tackle this, we employed **Multiple Logistic Regression of 3rd Degree**. Activation formula remains the same as for the model above, however the complexity increased due to the non-linear nature. We also found the accuracy to fluctuate due to higher degree and hence employed **Ridge Regularization** to combat those fluctuations to get the best overall accuracy.

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 018](https://user-images.githubusercontent.com/76467751/214298851-851b8946-9da8-4d54-8fd3-fad76dfd1e1c.png)

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 019](https://user-images.githubusercontent.com/76467751/214298872-f290de8f-65e9-4bd0-b194-5738741dd360.png)

Finally, for training the models, we had to find the **most optimal hyperparameters, learning rates and repetitions**. To do this we used **Nvidia’s GPU acceleration** using **CUDA** to run all the models hundreds of thousands of times with varying parameters. The **Beta values** of the model with best test accuracy and least error distance was stored separately for future use.

We also used **functions** to loop over **various values of n** and **learning rates** to find the pair with **best outputs**. A glimpse of the function created is as follows:

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 020](https://user-images.githubusercontent.com/76467751/214298905-3c2fb558-1513-4fe5-afa4-056d6bf00f6d.png)


A summary of the above details is given in the table below:

|S No.|Dataset Name|Output Type|Model Used|Details|
| :-: | :-: | :-: | :-: | :-: |
|1.|Salary|<p>Continuous</p><p>Number</p>|<p>Convolutional</p><p>` `Neural Network</p><p>(TensorFlow)</p><p>(Keras)</p>|<p></p><p>Hidden layer nodes: </p><p>**256 à128 à 64 à 32 à 16**</p><p>Connection Type: **Dense**</p><p>Optimizer: **adam**</p><p>Loss Metric: **Mean Square Error**</p><p>Max Epochs**: 100 (Early Stopping)**</p><p></p>|
|2.|Attrition|Binary|<p>Logistic Regression</p><p>(Ridge Regularization)</p>|<p></p><p>Max Iterations: **50000**</p><p>Learning Rate: **0.0001**</p><p>Regularization Constant: **0.2**</p><p>Activation Formula:* y=11+e-z***<br></p>|
|3.|Absenteeism|Binary|<p>Multiclass </p><p>Logistic Regression</p><p>(Ridge Regularization)</p>|<p></p><p>Max Iterations: </p><p>Learning Rate:</p><p>Regularization Constant: **0.2**</p><p>Activation Formula:* y=11+e-z*<br></p>|
|4.|Turnover|Binary|<p>Logistic Regression </p><p>of 3rd Degree</p><p>(Ridge Regularization)</p>|<p></p><p>Max Iterations: </p><p>Learning Rate:</p><p>Regularization Constant: **0.2**</p><p>Activation Formula:* y=11+e-z*<br></p>|



Technology Used – Score Predictor GUI

Our project utilises html, CSS and JavaScript to build the front end. We have used PyCharm to make the server to host the website on our local machine. We used Bootstrap to build the basic GUI form which is minimalistic and yet elegant to view. After that we made our own JavaScript functions to calculate the scores. The scores have been calculated using the input values of the form and the beta values of the four models. 

We do not import the model itself as importing the model would make the site heavy and incompatible with browsers incapable or running Python or .h5 compiled model files. Furthermore, we have made models using mathematical functions and hence making .h5 model file is not possible as that is a feature inbuilt into keras.

Following are screenshots of our output form and GUI:

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 021](https://user-images.githubusercontent.com/76467751/214298923-f78a765b-b109-4104-ab77-c162680c7872.png)

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 022](https://user-images.githubusercontent.com/76467751/214298956-28fbd72f-dcd4-4957-b728-dcfcd8a9cefb.png)

Dataset Description: Attrition


|Sr no.|Feature Name|Properties|Initial Values|Labelled as|Scaling factor|Correlation|
| :-: | :-: | :-: | :-: | :-: | :-: | :-: |
|1.|Age|<p>Integer</p><p>Discrete</p>|Range (18 – 60)||/10|0.72|
|2.|Business Travel|String|Non-Travel|0|/10|-0.61|
||||Travel-Frequently|1|||
||||Travel-Rarely|2|||
|3.|Department|String|HR|0|/10|0.71|
||||R&D|1|||
||||Sales|2|||
|4.|Distance From Home|<p>Integer</p><p>Discrete</p>|Range (1 – 29)||/10|0.81|
|5.|Education|<p>Integer</p><p>Discrete</p>|<p>Lowest – 1</p><p>Highest – 5</p>|||0.65|
|6.|Education Field|String|Humanities / HR|0|/10|0.73|
||||Life Sciences|1|||
||||Marketing|2|||
||||Medical|3|||
||||Other|4|||
||||Technical Degree|5|||
|7.|Environment Satisfaction|<p>Integer</p><p>Discrete</p>|<p>Lowest – 1</p><p>Highest – 5</p>|||-0.72|
|8.|Gender|<p>Integer</p><p>Discrete</p>|Female|0||-0.81|
||||Male|1|||
|9. |Job Involvement|<p>Integer</p><p>Discrete</p>|<p>Lowest – 1</p><p>Highest – 5</p>|||-0.83|
|10.|Job Level|<p>Integer</p><p>Discrete</p>|<p>Lowest – 1</p><p>Highest – 5</p>|||-0.86|
|<p>11.</p><p></p><p></p>|Job Role|String|Healthcare Rep.|0|/10|0.73|
||||HR|1|||
||||Lab Tech.|2|||
||||Manager|3|||
||||Manufacture Dir.|4|||
||||Research Dir.|5|||
||||Research Scientist|6|||
||||Sales Exec.|7|||
||||Sales Rep.|8|||
|12.|Job Satisfaction|<p>Integer</p><p>Discrete</p>|<p>Lowest – 1</p><p>Highest – 5</p>|||-0.87|
|13.|Marital Status|String|Divorced|0|/10|0.79|
||||Married|1|||
||||Single|2|||
|14.|Monthly Income|<p>Integer</p><p>Continuous </p>|<p>Range </p><p>(1,009 – 19,999)</p>||/1000|-0.88|
|15.|Companies Worked|<p>Integer</p><p>Discrete</p>|Range (0 – 9)|||0.77|
|16. |Over Time|Binary Class|No|0||-0.67|
||||Yes|1|||
|17.|Percent Salary Hike|<p>Integer</p><p>Discrete</p>|Range (10 – 25)||/10|-0.83|
|18.|Performance Rating|<p>Integer</p><p>Discrete</p>|<p>Lowest – 1</p><p>Highest – 5</p>|||-0.92|
|19.|Relationship Satisfaction|<p>Integer</p><p>Discrete</p>|<p>Lowest – 1</p><p>Highest – 5</p>|||-0.83|
|20.|Total Working Years|Integer<br>Discrete|Range (0 – 40)||/10|-0.67|
|21.|Training Time Last Year|Integer<br>Discrete|Range (0 – 10)|||0.66|
|22.|Work Life Balance|Integer<br>Discrete|<p>Lowest – 1</p><p>Highest – 5</p>|||-0.94|
|23.|Years at company|Integer<br>Discrete|Range (0 – 40)||/10|0.85|
|24.|Years at current role|Integer<br>Discrete|Range (0 – 20)||/10|0.87|
|25.|Years since last promotion|Integer<br>Discrete|Range (0 – 20)||/10|0.94|
|26.|Years with current manager|Integer<br>Discrete|Range (0 – 20)||/10|-0.83|




















Feature Description and purpose: Attrition

|Sr no.|Feature Name|Description/Purpose|
| :-: | :-: | :-: |
|1.|Age|To store the age of the employee. Age signifies generation and plays a major role in attrition.|
|2.|Business Travel|Divided into three categories to classify people who travel. 1 – 5 days a month is considered low (0), 6 – 12 days a month as medium (1) and above 12 days a week is considered high (3).|
|3.|Department|To choose the department in which the person works. Different departments have different attrition rates and depending on their work hours, culture and other internal workings.|
|4.|Distance From Home|Distance from home is an important feature to calculate attrition with high positive correlation. |
|5.|Education|Highest education received also has a positive correlation as higher education received often means more resistance to wear out due to the burden of work.|
|6.|Education Field|Different Educational fields have different attrition rates depending on their internal working, work difficulty, work hours etc. |
|7.|Environment Satisfaction|Ranging on a scale of 1 to 5, environment satisfaction records how satisfied is the person with their work environment. More satisfaction means less attrition and better performance of the employee.|
|8.|Gender|Even though we try and not be gender biased, yet different genders usually have different priorities and other engagements. All genders are psychologically different and hence it impacts their attrition values.|
|9.|Job Involvement|It is important for a person to be interested in their work and the more a person is involved the higher would be their interest in that particular line of work.|
|10.|Job Level|Job level has a major impact on attrition values. Often people on higher posts have less attrition as the responsibility of work and the sense of importance prevents them from degrading their quality of work.|
|11.|Job Role|Different job roles ranging from physical work to computer jobs impact how fast a person loses interest or becomes monotonous in their work.|
|12.|Job Satisfaction|It defines how satisfied is the employee with his or her work and hence impacts the attrition value.|
|13.|Marital Status|Marital status often implies that a person's time, effort and focus may be now divided. However, at the same time, it signifies a higher sense of responsibility and hence attrition may be less.|
|14.|Monthly Income|Income is one of the main incentives for a person to work. It is a high motivator and hence the salary coupled with the work position and other factors play a major role in employee attrition.|
|15.|Companies Worked|Higher number of companies worked in by an employee often mean lower focus span, lower patience and hence higher attrition.|
|16.|Over Time|If a person is working overtime, it may showcase their interest in their work and hence impacts attrition value as higher interest means lower attrition.|
|17.|Percent Salary Hike|Again, money is a big motivator for most employees and hikes in salary encourages employees to do better lowering their attrition values.|
|18.|Performance Rating|Evaluated by the manager or boss, the performance rating is a direct indication of the performance of that employee.|
|19.|Relationship Satisfaction|Relationship satisfaction often reflects on an employee’s work attitude and hence impacts their performance and hence their attrition values.|
|20.|Total Working Years|If an employee is working for more years, it implies a higher sense of responsibility and tolerance along with experience and hence usually amount to lower attrition values. Total working years along with companies worked in is a comprehensive factor to determine attrition values of employees.|
|21.|Training Time Last Year|Training time implies an employee’s willingness to change and learn new skills for their company and hence impact their attrition. |
|22.|Work Life Balance|Work life balance is an important factor. Ranging from 1 to 5, work life balance often |
|23.|Years at company|Time spent in the company often implies how much time a person stays in one company before moving on. Higher of this value implies lower attrition.|
|24.|Years at current role|Higher number of years working in the same role may imply higher experience and expertise or it may also intricate the saturation point of employees doing the same type of work.|
|25.|Years since last promotion|Promotions much like salary hike play an important role as a motivator and hence are important to calculate an employee's attrition.|
|26.|Years with current manager|Number of years with the current manager imply the employee’s willingness to work and highlights the quality of their work hence implying lower attrition values.|

Dataset Description: Turnover

|Sr no.|Feature Name|Properties|Initial Values|Labelled as|Scaling factor|Correlation|
| :-: | :-: | :-: | :-: | :-: | :-: | :-: |
|1.|Satisfaction Level|<p>Float</p><p>Continuous</p>|Range (0.01 – 1.00)|||-0.85|
|2.|Last Evaluation|<p>Float</p><p>Continuous</p>|Range (0.10 – 1.00)|||-0.60|
|3.|No. of Projects|<p>Integer</p><p>Discrete</p>|Range (0 – 9)|||-0.42|
|4.|Time Spent Company|<p>Integer</p><p>Discrete</p>|Range (1 – 10)||/10|-0.78|
|5.|Work Accident|Binary Class|No|0||0.67|
||||Yes|1|||
|6.|Promotions In Last 5 Years|Binary Class|No|0||-0.81|
||||Yes|1|||
|7.|Department|String|Accounting|0|/10|0.56|
||||HR|1|||
||||IT|2|||
||||Management|3|||
||||Marketing|4|||
||||Product Manager|5|||
||||R&D|6|||
||||Sales|7|||
||||Support|8|||
||||Technical|9|||
|8.|Salary|Multiclass|High|0||-0.89|
||||Low|1|||
||||Medium|2|||



Feature Description and purpose: Turnover

|Sr no.|Feature Name|Description/Purpose|
| :-: | :-: | :-: |
|1.|Satisfaction Level|Ranging from 0.01 to 1, Satisfaction Level has a high negative correlation on Turnover.|
|2.|Last Evaluation|Depending on when the Last evaluation of employee is done, Turnover of employee varies as a recent evaluation yield more accurate result. Hence in older evaluations an employee is given the benefit of doubt that he may have changed and hence their values are often biased towards non turnover.|
|3.|No. of Projects|Higher number projects worked on usually implies higher interest in the work and hence less turnover.|
|4.|Time Spent Company|Time spent in the last company often implies how much time a person stays in one company before moving on. Higher of this value implies lower turnover.|
|5.|Work Accident|To be filled by the employer this field signifies a person |
|6.|Promotions In Last 5 Years|Promotions much like salary hike play an important role as a motivator and hence are important to calculate an employee's attrition.|
|7.|Department|Different departments impact how fast a person loses interest or becomes monotonous in their work hence affecting the rate at which employees leave the company therefore affecting the turnover|
|8.|Salary|Income is one of the main incentives for a person to work. It is a high motivator and hence the salary coupled with the work position and other factors play a major role in employee turnover.|




Dataset Description: Absenteeism

|Sr no.|Feature Name|Properties|Initial Values|Labelled as|Scaling factor|Correlation|
| :-: | :-: | :-: | :-: | :-: | :-: | :-: |
|1.|Transport Expense|<p>Integer</p><p>Continuous</p>|Range (100 – 400)|||0.53|
|2.|Service Time|<p>Integer</p><p>Discrete</p>|Range (1 – 30)|||-0.44|
|3.|Age|<p>Integer</p><p>Discrete</p>|Range (18 – 60)|||0.67|
|4.|Disciplinary Failure|Binary|No|0||0.59|
||||Yes|1|||
|5.|Education|Multiclass|<p>Lowest – 1</p><p>Highest – 5</p>|||-0.70|
|6.|Children|<p>Integer</p><p>Discrete</p>|Range (0 – 5)|||0.39|
|7.|Social Drinker|Binary|No|0||0.64|
||||Yes|1|||
|8.|Social Smoker|Binary|No|0||0.61|
||||Yes|1|||
|9.|Pets|<p>Integer</p><p>Discrete</p>|Range (0 – 10)|||0.32|
|10.|Weight|<p>Integer</p><p>Continuous</p>|Range (50 – 120)|||0.29|
|11.|Height|<p>Integer</p><p>Continuous</p>|Range (150 – 200)|||-0.32|





Feature Description and purpose: Absenteeism

|Sr no.|Feature Name|Description/Purpose|
| :-: | :-: | :-: |
|1.|Transport Expense|Employees with higher transport expenses often opt for work from home and otherwise holidays as it saves on their transport expenditure|
|2.|Service Time|Time spent in the last company often implies how much time a person stays in one company before starting to take too many leaves of absence |
|3.|Age|Older age may imply health issues as well as engagements in children’s or grandchildren's affairs. Youngsters usually take less leaves.|
|4.|Disciplinary Failure|Employees with disciplinary issues often take more leaves as compared to others. This field is filled by the current or most recent employer|
|5.|Education|Employees with higher education often take less absences due their habit of maintaining attendance |
|6.|Children|Employees with more children may not find enough time to devote to the company. People with less children are motivated to work to provide for their children and since they are less in number hence, they can still give a lot to the company without taking too many holidays |
|7.|Social Drinker|Employees who often drink are prone to take more holidays as they develop a drinking habit |
|8.|Social Smoker|As with social drinkers, employees who often smoke are prone to take more holidays as they develop a smoking habit |
|9.|Pets|Employees with more pets may not find enough time to devote to the company. People with less pets are motivated to work to provide for their pets and since they are less in number hence, they can still give a lot to the company without taking too many holidays |
|10.|Weight|Together with height, weight implies a person's fitness which further showcases their dedication. Higher dedication means lesser absenteeism in general.|
|11.|Height|Together with weight, height implies a person's fitness which further showcases their dedication. Higher dedication means lesser absenteeism in general.|



Dataset Description: Salary

|Sr no.|Feature Name|Properties|Initial Values|Labelled as|Scaling factor|Correlation|
| :-: | :-: | :-: | :-: | :-: | :-: | :-: |
|1.|Job Type|String|CEO|0|/10|0.45|
||||CFO|1|||
||||CTO|2|||
||||Support Staff|3|||
||||Junior|4|||
||||Manager|5|||
||||Senior|6|||
||||VP|7|||
|2.|Degree|String|Bachelors|0|/10|0.68|
||||Doctoral|1|||
||||High School|2|||
||||Masters|3|||
||||None|4|||
|3.|Major|String|Biology|0|/10|0.72|
||||Business|1|||
||||Chemistry|2|||
||||Computer Science|3|||
||||Engineering|4|||
||||Literature|5|||
||||Math|6|||
||||None|7|||
||||Physics|8|||
|4.|Industry|String|Auto|0|/10|0.36|
||||Education|1|||
||||Finance|2|||
||||Health|3|||
||||Oil|4|||
||||Service|5|||
||||Web|6|||
|5.|Years of Service|<p>Integer</p><p>Discrete</p>|Range (0 – 25)||/10|0.69|
|6.|Miles from Home|<p>Integer</p><p>Discrete</p>|Range (0 – 99)||/100|-0.42|









Feature Description and purpose: Salary


|Sr no.|Feature Name|Description/Purpose|
| :-: | :-: | :-: |
|1.|Job Type|Different job types have different pays due to the different form of work that one has to do|
|2.|Degree|Different levels of highest degree fetch different pays. Higher a person has studied; more will be their skillset and hence would demand a higher pay scale|
|3.|Major|Majoring in different fields will fetch different pay according to the level of difficulty of that major along with demand and supply.|
|4.|Industry|Different industries have different pay scales according to demands and effort etc.|
|5.|Years of Service|Higher years of service imply more experience and skill and hence may demand higher salaries|
|6.|Miles from Home|Employees with higher transport expenses often need a slightly higher allowance for transportation. This need should be met by companies for better performance, lower attrition and turnovers|














**Output Screenshots

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 023](https://user-images.githubusercontent.com/76467751/214298995-7b3440a2-f63c-424d-b745-286ac7df9313.png)

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 024](https://user-images.githubusercontent.com/76467751/214299025-a88c258c-0e89-4c39-8adb-3db5f778b7aa.png)

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 025](https://user-images.githubusercontent.com/76467751/214299050-0d4bd3fc-86c4-4d3a-96cc-8fda46517350.png)

![Aspose Words 0c5aa5b8-8363-4085-bc25-097709bdd400 026](https://user-images.githubusercontent.com/76467751/214299072-0675973c-4a6e-4266-a77b-500fca1ae0e3.png)


