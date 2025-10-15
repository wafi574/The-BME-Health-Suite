# The-BME-Health-Suite
A multi-tab web application runs on a local device and provides users with vital health and fitness calculations. This app is built in Python and deployed with Gradio. The application is a fully featured tool with three tabs used for health and fitness app calculations and tracking Body Mass Index (BMI) , calculating Basal Metabolic Rate (BMR) and daily food intake logging.
# EGBI121 Mini project by Kritpatchara Wongkwan 6813353 and Wafi Alsawad 6813426

# calculating and tracking Body Mass Index (BMI)
This tab enables users to find out their BMI and keep track of it.
The backend function calculate_bmi() which derives the result using standard formula  BMI=weight(kg)hight(m)2 . convert_to_Metric() takes in measurements, and converts from imperial units (lbs, inches). find_bmi_category() for classification (e.g., "Normal", "Overweight").
The Pandas library keeps track of user history. The function save_bmi_data stores each score into a bmi_data.csv file. This historical data is presented using Plotly as an interactive line graph showing a user's BMI trend over time.
gr.Radio buttons for unit change, gr.Number inputs for height and weight  and gr.Textbox components to display the calculated BMI. The history is displayed in a gr.Plot component. 

# calculating Basal Metabolic Rate (BMR) 
This tab calculate user daily calorie intake
calculate_bmr() computes the user's Basal Metabolic Rate by applying the Harris-Benedict equation. calculate_tdee() computes the Total Daily Energy. find_daily_calories() returns a daily calorie goal by scaling the TDEE according to the user's selected goal (weight loss, maintain, gain).
The results are clearly shown in separate gr.Textbox components, displaying BMR, TDEE, and the daily calorie goal.

# Logging Daily Food Intake 
This tab tracks the user's daily nutrition.
process_food_log() allows users to add food items either from a predefined list of common foods (COMMON_FOODS dictionary) or by manual entry.
The function filters the data to display a summary of food consumed on a selected date. It also generate a Plotly bar chart, which visualizes daily calorie intake against the user's TDEE goal (imported from Tab 2).
gr.DateTime selector to pick a date, a gr.Radio button to switch between "Common Food" and "Manual Entry" , a gr.Dataframe to display the daily food log, and a gr.Plot to show the weekly progress chart.
