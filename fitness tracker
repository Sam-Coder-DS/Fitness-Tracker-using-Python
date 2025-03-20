import streamlit as st

def workout():
    st.subheader("Workout Tracker")
    yoga = st.number_input("Yoga (minutes)", min_value=0, value=0)
    cardio = st.number_input("Cardio (minutes)", min_value=0, value=0)
    meditation = st.number_input("Meditation (minutes)", min_value=0, value=0)
    total_time = yoga + cardio + meditation
    
    if total_time >= 60:
        score = 5.0
    elif total_time >= 48:
        score = 4.0
    elif total_time >= 36:
        score = 3.0
    elif total_time >= 24:
        score = 2.0
    else:
        score = 1.0
    
    st.write(f"Your fitness score is {score} on a scale of 5.0")

def BMI():
    st.subheader("BMI Calculator")
    height = st.number_input("Height (cm)", min_value=50.0, value=170.0)
    weight = st.number_input("Weight (kg)", min_value=10.0, value=60.0)
    bmi = weight / (height / 100) ** 2
    
    if bmi < 18.5:
        status = "Underweight"
    elif bmi < 25:
        status = "Normal"
    elif bmi < 30:
        status = "Overweight"
    else:
        status = "Obesity"
    
    st.write(f"Your BMI is {bmi:.2f} ({status})")

def waterIntake():
    st.subheader("Water Intake Calculator")
    weight = st.number_input("Weight (kg)", min_value=10.0, value=60.0)
    age = st.number_input("Age", min_value=1, value=25)
    
    weight_pounds = weight * 2.20462
    if age < 30:
        water_ml = weight_pounds * 40
    elif age < 55:
        water_ml = weight_pounds * 35
    else:
        water_ml = weight_pounds * 30
    
    water_liters = (water_ml / 28.3) * 0.0295735
    st.write(f"Recommended daily water intake: {water_liters:.2f} liters")

def BMR():
    st.subheader("BMR Calculator")
    height = st.number_input("Height (cm)", min_value=50.0, value=170.0)
    weight = st.number_input("Weight (kg)", min_value=10.0, value=60.0)
    age = st.number_input("Age", min_value=1, value=25)
    gender = st.radio("Gender", ["Male", "Female"])
    
    if gender == "Male":
        bmr = 66 + (6.2 * weight) + (12.7 * height) - (6.76 * age)
    else:
        bmr = 655.1 + (4.35 * weight) + (4.7 * height) - (4.7 * age)
    
    st.write(f"Your BMR is {bmr:.2f} calories/day")
    return bmr

def approxCalorieBurnt():
    st.subheader("Approximate Calorie Burn Calculator")
    bmr_value = BMR()
    activity_level = st.selectbox("Select your activity level", [
        "Little to no exercise", "Light exercise (1–3 days/week)", 
        "Moderate exercise (3–5 days/week)", "Hard exercise (6–7 days/week)", 
        "Extra active"
    ])
    
    factor = {"Little to no exercise": 1.2, "Light exercise (1–3 days/week)": 1.37, 
              "Moderate exercise (3–5 days/week)": 1.55, "Hard exercise (6–7 days/week)": 1.725, 
              "Extra active": 1.9}[activity_level]
    
    calories = bmr_value * factor
    st.write(f"Calories needed to maintain weight: {calories:.2f} kcal/day")

st.title("Fitness Tracker")
option = st.sidebar.selectbox("Choose a feature", ["Workout", "BMI", "Water Intake", "BMR", "Calorie Burn"])

if option == "Workout":
    workout()
elif option == "BMI":
    BMI()
elif option == "Water Intake":
    waterIntake()
elif option == "BMR":
    BMR()
elif option == "Calorie Burn":
    approxCalorieBurnt()
