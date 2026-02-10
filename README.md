# Ex.04 Design a Website for Server Side Processing
## Name:Nithish D M
## Date:10/02/2026

## AIM:
To create a web page to calculate vehicle mileage and fuel efficiency using server-side scripts.

## FORMULA:
M = D / F
<br> M --> Mileage (in km/l)
<br> D --> Distance Travelled (in km)
<br> F --> Fuel Consumed (in l)

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM:
```
views.py
from django.shortcuts import render
def mileage(request):
    d=float(request.POST.get('distance','0'))
    f=float(request.POST.get('fuel_consumed','0'))
    mileage=d/f if request.method=='POST' else 0
    print("distance =",d)
    print("fuel_consumed =",f)
    print("mileage =",mileage)
    return render(request,'mathapp/math.html',{'d':d,'f':f,'mileage':mileage})

urls.py
from django.contrib import admin
from django.urls import path
from mathapp import views
urlpatterns = [
    path('',views.mileage,name='mileage'),
]

math.html
<html>
    <head>
        <title>Mileage Calculator</title>
        <style>
            .box
            {
                width: 500px;
                height: 300px;
                border: dashed 3px blueviolet;
                padding:10 px;
                position:fixed;
                top:190px;
                left:500px;
                text-align:center;
                background-color:hotpink;
            }
        </style>
    </head>
    <body bgcolor="lightyellow">
        <div class="box">
            <h1>Mileage Calculator</h1>
            <h3>POPURI SAHITHYA(25004681)</h3>
        <form method="POST">
        {% csrf_token %}
            <div class="formelt">       
            <label>Distance(in km)</label>
            <input type="text" name="distance" required></input>
            </div>
            <br>
            <div class="formelt">
            <label>Fuel_consumed(in l)</label>
            <input type="text" name="fuel_consumed" required></input>
            </div>
            <br>
            <div class="formelt">
            <input type="submit" value="Calculate">
            </div>
            <br>
            <div class="formelt">
            <label>Mileage:(in km/l)</label>
            <input type="text" name="mileage" value="{{mileage}}"></input>
            </div>
            <br>
        </form>
        </div>
    </body>
</html>
```

## OUTPUT - SERVER SIDE:
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/f802c03d-9aca-40cb-b138-8ee1cc7eca7e" />

## OUTPUT - WEBPAGE:
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/c28345e5-bbbf-4bb9-b109-492e3cc12a96" />

## RESULT:
The a web page to calculate vehicle mileage and fuel efficiency using server-side scripts is created successfully.
