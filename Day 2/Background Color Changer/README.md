# Tip Calculator Application

## Overview
This is a simple Tip Calculator application designed to calculate the tip amount based on the bill amount, service quality, and the number of people sharing the bill. The application uses HTML, CSS, and JavaScript for implementation.

## Features
- **Input Fields:**
  - Bill Amount
  - Service Quality (with percentage options)
  - Number of People Sharing the Bill
- **Dynamic Tip Calculation:**
  - Displays the calculated tip amount.
  - Handles cases where only one person is paying or multiple people are sharing the bill.
- **Responsive UI:**
  - Styled using CSS for a clean and user-friendly appearance.

## File Structure
```
├── index.html
├── css
│   └── style.css
└── js
    └── index.js
```

### File Descriptions
1. **index.html:** Contains the structure of the Tip Calculator with input fields, dropdowns, and a calculate button.
2. **style.css:** Provides styling for the calculator, including layout, colors, and button designs.
3. **index.js:** Contains the JavaScript logic for calculating the tip based on user inputs.

## How to Use
1. Clone the repository or download the files to your local machine.
2. Open the `index.html` file in your preferred web browser.
3. Follow these steps to calculate the tip:
   - Enter the bill amount.
   - Select the service quality from the dropdown menu.
   - Enter the number of people sharing the bill.
   - Click the "Calculate" button.
4. The tip amount will be displayed below the button.

## Key Logic in JavaScript
### Tip Calculation Function
```javascript
function tipCalculator() {
    var billAmount = document.getElementById("bill").value;
    var serviceQuality = document.getElementById("service").value;
    var numberOfPeople = document.getElementById("numOfPeople").value;

    if (billAmount === "" || serviceQuality == 0) {
        alert("Please enter required values!");
        return;
    }

    if (numberOfPeople === "" || numberOfPeople <= 1) {
        numberOfPeople = 1;
        document.getElementById("each").style.display = "none";
    } else {
        document.getElementById("each").style.display = "block";
    }

    var totalAmount = (billAmount * serviceQuality) / numberOfPeople;
    totalAmount = Math.round(totalAmount * 100) / 100;
    totalAmount = totalAmount.toFixed(2);
    document.getElementById("tip-container").style.display = "block";
    document.getElementById("tip").innerHTML = totalAmount;
}
```
### Event Listener for Calculate Button
```javascript
document.getElementById("calculate-btn").onclick = function() {
    tipCalculator();
};
```

## Styling Highlights (CSS)
- **Container Design:**
  - Rounded corners and shadow effects for a clean and modern look.
  - Linear gradient background for added depth.
- **Button Design:**
  - Green background with rounded corners.
  - Padding for better clickability.

### Example CSS
```css
body {
    background: green;
}
.container {
    font-family: Georgia, 'Times New Roman', Times, serif;
    text-align: center;
    height: 100%;
    width: 50%;
    padding: 2rem 0;
    margin: 7rem 0 0 20rem;
    border-radius: 50px;
    background: linear-gradient(145deg, #ffffff, #e6e6e6);
    box-shadow: 20px 20px 60px #d9d9d9, -20px -20px 60px #ffffff;
}
#calculate-btn {
    background-color: green;
    border-radius: 20px;
    padding: 10px 20px;
}
```

## Future Enhancements
- Add real-time validation for inputs.
- Make the application fully responsive for different screen sizes.
- Include additional currency options.
- Add animations for a more engaging user experience.

## License
This project is open-source and available for use under the MIT License.

---
Thank you for using the Tip Calculator! Feel free to customize and improve it as per your needs.
