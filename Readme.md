# Ex06 BMI Calculator
## Date: 19/11/25

## AIM
To create a BMI calculator using React Router 

## ALGORITHM
### STEP 1 State Initialization
Manage the current page (Home or Calculator) using React Router.

### STEP 2 User Input
Accept weight and height inputs from the user.

### STEP 3 BMI Calculation
Calculate the BMI based on user input.

### STEP 4 Categorization
Classify the BMI result into categories (Underweight, Normal weight, Overweight, Obesity).

### STEP 5 Navigation
Navigate between pages using React Router.

## PROGRAM

```


import React, { useState } from "react";
import { BrowserRouter as Router, Routes, Route, Link } from "react-router-dom";

// Home Page
function Home() {
  return (
    <div style={{ textAlign: "center", marginTop: "60px" }}>
      <h1>Welcome</h1>
      <p>Simple BMI Calculator using React Router</p>
      <Link to="/bmi" style={{ fontSize: "20px" }}>Go to BMI Calculator</Link>
    </div>
  );
}

// BMI Calculator Page
function BMICalculator() {
  const [height, setHeight] = useState("");
  const [weight, setWeight] = useState("");
  const [bmi, setBMI] = useState(null);

  const calculateBMI = () => {
    if (!height || !weight) return;
    const h = height / 100; // convert cm to meters
    const result = (weight / (h * h)).toFixed(2);
    setBMI(result);
  };

  return (
    <div style={{ textAlign: "center", marginTop: "60px" }}>
      <h1>BMI Calculator</h1>

      <input
        type="number"
        placeholder="Height in cm"
        value={height}
        onChange={(e) => setHeight(e.target.value)}
        style={{ margin: "10px", padding: "8px", width: "200px" }}
      />
      <br />

      <input
        type="number"
        placeholder="Weight in kg"
        value={weight}
        onChange={(e) => setWeight(e.target.value)}
        style={{ margin: "10px", padding: "8px", width: "200px" }}
      />
      <br />

      <button
        onClick={calculateBMI}
        style={{ padding: "10px 20px", marginTop: "10px", cursor: "pointer" }}
      >
        Calculate
      </button>

      {bmi && (
        <h2 style={{ marginTop: "20px" }}>Your BMI: {bmi}</h2>
      )}

      <br />
      <Link to="/" style={{ marginTop: "20px", display: "inline-block" }}>Go Back</Link>
    </div>
  );
}

// Main App with Router
export default function App() {
  return (
    <Router>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/bmi" element={<BMICalculator />} />
      </Routes>
    </Router>
  );
}


```

## OUTPUT

<img width="1908" height="1033" alt="image" src="https://github.com/user-attachments/assets/1a2cde8f-7d4a-4f18-a0e9-e357b4a7170a" />


## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
