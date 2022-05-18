# Medbot
Med-Bot is a virtual medical assistant or we use a chatbot which analyze customer’s symptoms and predict the ailments.<br>

<b>Chatbot Design</b><br>
Med-Bot is implemented in python using numpy,sci-kit learn and pandas module for testing and training the machine learning model. Decision tree classification is used to traverse through the data-set and retrieve the sequence of decisions traversed. Every Symptom is stored in the form of columns under a disease row and hence same disease may have various symptoms which map to different levels of suggestions and severity. The data-set is encoded which means that diseases symptoms are assigned numerical values which act as the anchor point in the deciding the severity, generating patient report and ascertaining confidence levels.<br>

<b>Pattern Detection</b><br>
The list of symptoms entered is finite and the user can enter any symptom and a perfect string match from the data-set ensures further questions being provided by the med-bot can be answered by the user. Data is validated and invalid symptoms are displayed as a warning message.
Regular expression match used: String_matched= "^" + inp + "$"

<b>Medical Data Storage Design</b><br>
Raw data is stored in 3 files.<br>
1.dataset.csv<br>
2.training.csv<br>
3.testing.csv<br>

This is the Knowledge base of the application and the med-bot retrieves data and computes its result on this given data set. Here the training-testing ratio is 70:30 which means that 70 percent of the examples are trained to fit the model and the remaining 30 percent is used to test the accuracy of the model.
<br>
<br>The database for result display:<br>
1.symptom_Description.csv<br>
2.symptom_severity.csv<br>
3.symptom_precautions.csv<br>

<br>These files are used in report generation and serve as the interactive result to the user’s answer in response to med-bot’s queries.<br>
<br><b>Shortlisting Diseases</b><br>
Concatenating the symptoms entered by the user and backtracking it to correct root node ,which is disease helps to select an array of same diseases.
<br><b>Detecting Disease</b><br>
After the Diseases are shortlisted the severity value is used to distinguish from the vector the first element and return the result tree of that node recursively.
<br><b>Consultation Process</b><br>
The process of consultation is ascertained on the numerical value of severity or the weightage given to the set of symptoms based on Information from medical databases like informatica and the correct the reply to the query is displayed regarding the precautions and the need to visit the doctor.<br>
The consultation process takes place in the following manner -<br><br>
a. Questioning Symptoms<br>
The Chatbot questions the user about the symptoms from the symptom severity .csv record. The then adds up the score of the symptom to the seriousness score of the disease for every symptom that matches with the user's problem. If the symptom matches with the user's condition, the respective medication fed in that particular symptom gets added in the medication vector and the similar thing happens for the precautions section.<br><br>
b. Threshold Checking<br>
To initiate this process, the seriousness score should hit above the threshold level. Following this the message to consult doctor or not based on the number of days the symptom last is calculated. At the end the confidence level of diagnosis is presented which represents accuracy of training model to correctly identify the disease from the database.<br><br>
 
<b>Formulas:</b><br>
1. H=Σ (Score)*number of days symptoms last/ Threshold Value<br>
H = It is the decision parameter which is used to check if the threshold level was hit.<br>
Σ (Score) = It is the sum total score of all the symptoms that the user experiences.<br>
Threshold-Value = It is the upper limit value which the Med-bot can handle.<br><br>
2.confidence_level = (Number of symptoms present)/Number of symptoms given)<br>

