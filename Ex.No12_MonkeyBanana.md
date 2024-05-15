# Ex.No: 13 Learning – Use Supervised Learning  
### DATE: 22/04/24                                                                           
### REGISTER NUMBER : 212221040036
### AIM: 
To write a program to train the classifier for prediciting diabetes
###  Algorithm:
```
1. Load, preprocess, and train a neural network model on diabetes data.
2. Split, scale, and evaluate model accuracy on test data.
3. Define a function for predicting diabetes based on input variables.
4. Create a Gradio interface for interactive predictions.
5. Deploy the interface for users to input health indicators and receive predictions.
```

### Program:
```python
import numpy as np
import pandas as pd

pip install gradio

pip install typing-extensions --upgrade

!python --version

pip install --upgrade typing

import gradio as gr

import pandas as pd

cd /content/gdrive/MyDrive/demo/gradio_project-main

#get the data
data = pd.read_csv('/content/diabetes.csv')
data.head()

print(data.columns)

x = data.drop(['Outcome'], axis=1)
y = data['Outcome']
print(x[:5])

#split data
from sklearn.model_selection import train_test_split

x_train, x_test, y_train, y_test= train_test_split(x,y)

#scale data
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
x_train_scaled = scaler.fit_transform(x_train)
x_test_scaled = scaler.fit_transform(x_test)

#instatiate model
from sklearn.neural_network import MLPClassifier
model = MLPClassifier(max_iter=1000, alpha=1)
model.fit(x_train, y_train)
print("Model Accuracy on training set:", model.score(x_train, y_train))
print("Model Accuracy on Test Set:", model.score(x_test, y_test))

print(data.columns)

#create a function for gradio
def diabetes(Pregnancies, Glucose, Blood_Pressure, SkinThickness, Insulin, BMI,Diabetes_Pedigree, Age):
    x = np.array([Pregnancies,Glucose,Blood_Pressure,SkinThickness,Insulin,BMI,Diabetes_Pedigree,Age])
    prediction = model.predict(x.reshape(1, -1))
    if(prediction==0):
      return "NO"
    else:
      return "YES"

outputs = gr.Textbox()
app = gr.Interface(fn=diabetes, inputs=['number','number','number','number','number','number','number','number'], outputs=outputs,description="Detection of Diabeties")
app.launch(share=True)
```

### Output:
![image](https://github.com/Bhargava-Shankar/AI_Lab_2023-24/assets/85554376/e921a004-8ec7-415f-8fab-dcaa71758db2)



### Result:
Thus the system was trained successfully and the prediction was carried out.
