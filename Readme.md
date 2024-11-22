# **Bacteria Growth Prediction Using Milne's and Taylor Methods**

## **Overview**
This project implements numerical methods to predict bacterial population growth using the **Milne's Method** and **Taylor Series Method**. These techniques are applied to the logistic growth model, a widely used model in population dynamics.

The project includes features such as:
- Initial Population Size
- Growth Rate
- Carrying Capacity
- Time Step
- Number of Steps

---

## **Features**

### **1. Initial Population Size (\(P_0\))**
The starting size of the bacterial population at time \(t = 0\). This parameter defines the initial state of the simulation.

### **2. Growth Rate (\(r\))**
The rate at which the population grows under ideal conditions. Higher values of \(r\) result in faster population growth.

### **3. Carrying Capacity (\(K\))**
The maximum population size that the environment can support. Growth slows as the population approaches \(K\).

### **4. Time Step (\(h\))**
The interval between each step in the numerical simulation. Smaller values of \(h\) improve accuracy but require more computation.

### **5. Number of Steps**
The total number of time steps for the simulation. This determines the duration of the prediction.

---

## **Logistic Growth Model**
The logistic growth model is represented by the following differential equation:

\[
\frac{dP}{dt} = rP \left(1 - \frac{P}{K}\right)
\]

Where:
- \(P\): Population size
- \(r\): Growth rate
- \(K\): Carrying capacity

---

## **Numerical Methods**

### **1. Milne's Method**
Milne's method is a predictor-corrector technique for solving ordinary differential equations (ODEs). It involves:
- Predicting the population size at the next step.
- Correcting the predicted value for improved accuracy.

Steps:
1. Predict \(P_{n+1}\) using:
   \[
   P_{n+1} = P_{n-3} + \frac{4h}{3} \left(2f(P_n) - f(P_{n-1}) + 2f(P_{n-2})\right)
   \]
2. Correct \(P_{n+1}\) using:
   \[
   P_{n+1}^{(corrected)} = P_{n-1} + \frac{h}{3} \left(f(P_{n-2}) + 4f(P_{n-1}) + f(P_n)\right)
   \]

### **2. Taylor Series Method**
Taylor's method uses a truncated Taylor expansion to approximate the population size at each time step.

Steps:
1. Express \(P(t+h)\) as:
   \[
   P(t+h) = P(t) + hP'(t) + \frac{h^2}{2!}P''(t) + \dots
   \]
2. Compute derivatives \(P'(t)\), \(P''(t)\), etc., using the logistic growth equation:
   \[
   P'(t) = rP\left(1 - \frac{P}{K}\right)
   \]

---

## **Project Workflow**
1. **Input Parameters**:
   - Initial population size (\(P_0\)).
   - Growth rate (\(r\)).
   - Carrying capacity (\(K\)).
   - Time step (\(h\)).
   - Number of steps (\(N\)).

2. **Compute Initial Values**:
   - Use Taylor series method to bootstrap the first few steps for Milne's method.

3. **Simulate Population Growth**:
   - Apply Milne's method to predict population sizes over time.

4. **Visualize Results**:
   - Plot population size vs. time.
   - Compare results from Milne's and Taylor methods.

---

## **How to Use**
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/bacteria-growth-prediction.git
   cd bacteria-growth-prediction
