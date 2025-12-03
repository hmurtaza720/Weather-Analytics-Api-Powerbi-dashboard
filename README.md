# 🌦️ Weather Analytics Power BI Dashboard  
**Real-Time Weather • Air Quality Index (AQI) • 7-Day Forecast**

<img width="1149" height="649" alt="image" src="https://github.com/user-attachments/assets/7348ef7a-ead3-4fce-b913-7373588a6efe" />


A modern, API-powered **Weather Analytics Dashboard** built in **Power BI**, integrating real-time weather, air quality, and forecast trends through **WeatherAPI**.  
This project highlights API integration, advanced DAX, clean UI/UX, and professional BI development.

---

## 🔍 Overview
This dashboard provides:

- 📡 **Real-time weather metrics** (Temperature, Humidity, Wind, Pressure)  
- 🏙️ **Air Quality Index (AQI)** with health classifications  
- 📈 **7-Day Weather Forecast**  
- 🌧️ **Rain Probability indicators**  
- 🗺️ **Dynamic city selection**  
- 🖥️ **Modern glassmorphism UI**

---

## 🛠️ Technologies Used
- **Power BI**
- **DAX**
- **Power Query (M Language)**
- **WeatherAPI**
- **JSON Parsing**
- **Data Modeling & Visualization**

---

## 📊 Dashboard Features

### **1. Real-Time Weather KPIs**
- Temperature (°C)  
- Humidity (%)  
- Wind Speed (km/h)  
- Pressure (hPa)  
- UV Index  
- Visibility  

### **2. Air Quality Index (AQI)**
AQI components include:  
- PM2.5, PM10  
- CO, NO₂, SO₂  
- Ozone (O₃)  

Includes DAX-based rating labels:  
- 🟢 Good  
- 🟡 Moderate  
- 🔴 Unhealthy  

### **3. 7-Day Weather Forecast**
- Daily High & Low Temperatures  
- Weather Conditions (Sunny, Cloudy, Rainy)  
- Rain Probability  
- Line chart with trends  

### **4. City Search Integration**
- API parameter controls  
- Weather auto-refreshes per city  

---

## 📡 API Used

**WeatherAPI Endpoint:**
http://api.weatherapi.com/v1/current.json?key=43cc1ceac2b74ccda1892416252611&q=Karachi&aqi=no


Data parsed via Power Query → transformed → DAX → visualized.

---

## 🧮 DAX Measures (Appendix)

### **Temperature**
```DAX
Temperature_C = SELECTEDVALUE(Weather[Temp_C])

AQI Status =
SWITCH(
    TRUE(),
    [AQI] <= 50, "Good",
    [AQI] <= 100, "Moderate",
    [AQI] <= 150, "Unhealthy",
    "Very Unhealthy"
)

FeelsLike = SELECTEDVALUE(Weather[FeelsLike_C])

Wind Level =
SWITCH(
    TRUE(),
    [Wind] < 10, "Breeze",
    [Wind] < 20, "Windy",
    "Strong Winds"
)
```
---

### **🧹 Data Transformation (Power Query M)**
Key transformation steps:

-Expand JSON nested objects
-Convert lists → rows
-Promote headers
-Rename fields
-Add calculated columns (visibility, feels like, rain %)
-Set correct data types




### **UI/UX Design Notes**
-Clean minimal layout
-Soft shadows & rounded edges
-Weather icons
-Color-coded AQI badges
-Spacing optimized for readability

### **🚀 How to Run**

-Download or clone the repository
-Open .pbix file in Power BI Desktop
-Go to Transform Data → Parameters
-Add your WeatherAPI Key
-Click Refresh All


### **📬 Contact**

- Syed Murtaza Hassan
- Data Analyst & BI Developer
- LinkedIn: www.linkedin.com/in/syed-murtaza-hassan-rizvi-736795279
- Email: hmurtaza510@gmail.com




