# Ex.03 Design a Website for Server Side Processing
## Date: 10-11-2026

## AIM:
To create a web page to calculate Churn Rate using server-side scripts.

## FORMULA:
Churn Rate = (CustLost / InitCust) * 100
<br> InitCust --> Initial Customers Count
<br> CustLost --> Customers Lost Count

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create a HTML file to implement form based input and output.

### Step 5:
Create python programs for views and urls to perform server side processing.

### Step 6:
Receive input values from the form using request.POST.get().

### Step 7:
Calculate the Result using the given formula.

### Step 8:
Display the calculated result in the server console.

### Step 9:
Render the result to the HTML template.

### Step 10:
Publish the website in Localhost.

## PROGRAM:
```
abcd.html
<html>
    <head>
        <title>CHURN RATE CALCULATOR</title>
    </head>
    <body>
        <center><i><h1>CHURN RATE CALCULATOR</h1></i></center>
        <center><h2>Dhivakar(26019255)</h2></center>
        

    <form method="POST">
        {% csrf_token %}<br>

        <label>CustLost:</label>
        <input type="text" name="{{ CustLost }}"><br><br>
        <label>InitCust:</label>
        <input type="text" name="{{ InitCust }}"><br><br>
        <input type="submit" value="Calculate"><br><br> 
        <label>Churn Rate:</label>
        <input type="text" value="{{ ChurnRate }}">
    </form>
    </body>
</html>

views.py
from django.shortcuts import render
def calculate(request):
    custlost = int(request.POST.get('price', '0'))
    initlost = int(request.POST.get('gst', '0'))
    bill = initlost + (initlost * custlost / 100) if request.method == 'POST' else 0
    print("initial customer =",initlost)
    print("customer lost =",custlost)
    print("churn rate =",bill)
    return render(request, 'dhiva/abcd.html',{'initlost': initlost, 'custlost': custlost, 'bill': bill})

urls.py
from django.contrib import admin
from django.urls import path
from dhiva import views

urlpatterns = [path('', views.calculate, name='calculate'),]

```


## OUTPUT - SERVER SIDE:
![alt text](<Screenshot 2026-11-13 135049.png>)


## OUTPUT - WEBPAGE:
![alt text](<Screenshot 2026-11-13 135132.png>)


## RESULT:
The the web page to calculate Churn Rate using server-side scripts is created successfully.
