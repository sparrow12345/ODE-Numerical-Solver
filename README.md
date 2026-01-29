# ODE Numerical Solver

## Overview
This project is a Python application for estimating solutions of ordinary differential equations (ODEs) using standard numerical methods. The differential equation, initial conditions, and numerical parameters are fully configurable by the user.

The application allows visual comparison between different numerical methods and an exact solution (when provided), along with basic error analysis.

---

## Features
- Numerical approximation of ODE solutions
- Pluggable numerical methods:
  - Euler Method
  - Improved Euler Method
  - Runge–Kutta Method (4th order)
- Optional exact solution for comparison
- Graphical visualization
- Error analysis:
  - Global error
  - Local error
  - Step size vs. error

---

## Application Pages
The GUI consists of four navigable views:
1. **Graphs** – solution plots
2. **Global Errors**
3. **Local Errors**
4. **Step Size vs. Error**

---

## Configuration
Users can configure:
- Initial conditions `(x0, y0)`
- Differential equation
- Step size
- Plot range (grid size)

> **Note:** When using an exact solution, the initial conditions must be consistent with it to ensure valid comparisons.

---

## Architecture
The application is implemented using:
- Object-Oriented Programming
- MVC (Model–View–Controller) pattern

### Design Principles
- **Single Responsibility Principle**  
  Model, View, and Controller components are clearly separated.
- **Liskov Substitution Principle**  
  Numerical methods share a common interface and are interchangeable.
- **Interface Segregation Principle**  
  Numerical method interfaces expose only required functionality.

---

## Core Interfaces

### Numerical Method Base Class
```python
class DENumericalMethod:
    def __init__(self, derivative_expr):
        self.derivative_expr = derivative_expr

    def compute(self, x0, y0, x_limit, step):
        raise NotImplementedError

