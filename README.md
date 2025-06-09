# PUSH-BUTTON-COUNTER
"COMPANY": CODTECH IT SOLUTIONS
"NAME": GANAVI AL
"INTERN ID": CT04DG130
"DOMAIN": EMBEDDED SYSTEM
"DURATION": 4 WEEKS
"MENTOR": NEELA SANTHOSH


### 🔧 **Introduction**

A push button counter is a simple electronic project that uses an Arduino to count how many times a button is pressed. It is commonly used in learning environments to understand how digital inputs work and how microcontrollers handle button presses. In this project, we will use Tinkercad – a free online circuit simulator – to create and simulate a push button counter. Each time the button is pressed, the counter will increase by one and display the result on the Serial Monitor.

---

### 🎯 **Objective**

The main goal of this project is to design and simulate a push button-based counting system using Arduino in Tinkercad. The count will be displayed on the Serial Monitor or an optional 7-segment display or LCD. The counter will increment with each button press, and simple logic will be used to prevent multiple counts from a single press (debouncing).

---

### 🧰 **Components Required**


* **Arduino Uno** – The microcontroller that reads the input and handles counting.
* **Push Button** – A digital input device used to trigger the count.
* **Breadboard** – To make circuit connections.
* **10kΩ Resistor** – Used as a pull-down resistor to stabilize the button input.
* **Jumper Wires** – For connections.
* **(Optional)**: 7-Segment Display or LCD – To show the count visually instead of using the Serial Monitor.

---

### ⚙️ **Circuit Design in Tinkercad**

1. **Place the Arduino Uno** on the workspace.
2. **Add a breadboard** next to the Arduino.
3. **Insert the push button** into the breadboard across the middle gap.
4. **Connect one side of the button** to 5V.
5. **Connect the other side of the button** to Arduino **digital pin 2** and also to **GND through a 10kΩ resistor** (this acts as a pull-down resistor to avoid false triggers).
6. **Use jumper wires** to make all connections.
7. You may optionally connect a **7-segment display** or **LCD** to show the count visually, but we’ll use the Serial Monitor for simplicity.

---

### 💡 **Working Principle**

* The Arduino checks the state of the button.
* When the button is pressed (input goes HIGH), it adds one to a counter variable.
* To prevent counting multiple times during one press (due to button bounce), a delay is added after each valid press.
* The current count is then printed to the Serial Monitor.

---

### 🧾 **Arduino Code**

```cpp
int buttonPin = 2;     // Button is connected to pin 2
int count = 0;         // Counter variable
int lastState = LOW;   // To store the previous button state

void setup() {
  pinMode(buttonPin, INPUT);
  Serial.begin(9600);
}

void loop() {
  int currentState = digitalRead(buttonPin);
  
  // Detect button press (change from LOW to HIGH)
  if (currentState == HIGH && lastState == LOW) {
    count++;
    Serial.println("Count: " + String(count));
    delay(200); // Delay to debounce the button
  }

  lastState = currentState;
}
```

---

### 🖥️ **Output**

Once the circuit and code are uploaded in Tinkercad:

* Press the push button.
* Each press increases the count by one.
* The updated count is displayed on the **Serial Monitor** (Tools > Serial Monitor in Tinkercad).

---

### 🔍 **Applications**

* Basic learning project in Arduino and embedded systems.
* Can be extended to multiple buttons for up/down counting.
* Useful in making digital tally counters or score counters.

---

### ✅ **Conclusion**

The Push Button Counter in Tinkercad is a beginner-friendly project that helps you understand digital input, button debouncing, and serial output using Arduino. It is easy to build, simulate, and expand. This project also lays the foundation for more advanced applications involving user input and display systems.

#output

![Image](https://github.com/user-attachments/assets/602a8bea-c0dc-4ccb-b162-bc2039d99a72)


