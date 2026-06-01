# Ex04 Simple Calculator - React Project
## Date: 1/06/2026

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
**App.jsx**
```jsx
import { useState } from "react";
import "./App.css";

const keys = [
    "C",
    "/",
    "*",
    "-",
    "7",
    "8",
    "9",
    "+",
    "4",
    "5",
    "6",
    ".",
    "1",
    "2",
    "3",
    "0",
    "=",
];

function App() {
    const [value, setValue] = useState("0");

    const press = (key) => {
        if (key === "C") return setValue("0");
        if (key === "=")
            return setValue(() => {
                try {
                    return String(new Function(`return ${value}`)());
                } catch {
                    return "Error";
                }
            });
        setValue(value === "0" || value === "Error" ? key : value + key);
    };

    return (
        <main className="calc">
            <div className="display">{value}</div>
            <div className="keys">
                {keys.map((key) => (
                    <button
                        key={key}
                        className={
                            key === "=" ? "equal" : key === "C" ? "clear" : ""
                        }
                        onClick={() => press(key)}
                    >
                        {key}
                    </button>
                ))}
            </div>
        </main>
    );
}

export default App;


```

**App.css**
```css
#root {
    min-height: 100vh;
    display: grid;
    place-items: center;
    background: #111827;
}

.calc {
    width: min(320px, 92vw);
    padding: 16px;
    border-radius: 20px;
    background: #1f2937;
    box-shadow: 0 20px 50px rgba(0, 0, 0, 0.35);
}

.display {
    margin-bottom: 12px;
    padding: 18px 14px;
    border-radius: 12px;
    background: #0f172a;
    color: #f8fafc;
    font-size: 2rem;
    text-align: right;
    overflow: hidden;
}

.keys {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

button {
    border: 0;
    border-radius: 12px;
    padding: 14px 0;
    font: inherit;
    font-size: 1.1rem;
    background: #334155;
    color: #fff;
}

.clear {
    background: #b91c1c;
}

.equal {
    grid-column: span 4;
    background: #2563eb;
}


```


## OUTPUT
<img width="846" height="481" alt="image" src="https://github.com/user-attachments/assets/42af9828-3d32-4771-a22b-3c1a1eb98497" />



## RESULT
The program for developing a simple calculator in React.js is executed successfully.
