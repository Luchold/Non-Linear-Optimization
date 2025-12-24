# Cutting of Circular Disks from a Rectangular Steel Plate

##  Project Description

Many industrial manufacturing processes involve cutting specific geometric shapes from a raw material. After cutting, unused material is often discarded, resulting in a loss of steel and wasted money.

This project focuses on cutting **four circular disks** with variable radii **R_1, R_2, R_3, R_4**  from a rectangular steel plate.The objective is to **minimize the waste of steel**, i.e., maximize the total area covered by the circular disks while ensuring that:

- All disks fit inside the rectangle,
- No disks overlap.

This leads to a **nonlinear constrained optimization problem**.



##  Mathematical Formulation

We want to place four circles inside a rectangle of dimensions:

- **length**:  a 
- **width**: b 

We place the origin (0,0) at the lower-left corner of the rectangle.

### **Decision variables**

For each disk i in {1,2,3,4} we denote the :

- center:  (x_i, y_i)
- radius: R_i

### **Objective**

Maximize the total area of the four disks:

min{ab-pi(R_1^2+R_2^2+R_3^2+R_4^2)}



##  Constraints

###  **1. Boundary Constraints (circle must stay inside the rectangle)**

For each circle:
R_i <= x_i <= a - R_i

R_i <= y_i <= b - R_i

These ensure that the circle does not cross any of the four borders:
 x = 0,
x = a,
 y = 0,
 y = b

### **2. Non-Overlapping Constraints**

For any two circles i and j:

d(c_i, c_j)>= R_i + R_j where d(c_i, c_j) is the distance between the circle center


##️ Method: Using GEKKO

We use the **GEKKO** Python package to solve this nonlinear constrained optimization problem.

Steps:<br/>
- Define the rectangle dimensions a, b<br/>
- Create GEKKO variables for centers and radii<br/>
- Apply boundary and non-overlap constraints<br/>
- Define objective (maximize total area)<br/>
- Solve numerically<br/>
- Plot the resulting configuration<br/>

##  How to Execute the Code

Go to the folder **`notebook/`** and open the Jupyter Notebook:

waste_minimization.ipynb

Run all cells to:<br/>
- build the optimization model,<br/>
- solve the problem with GEKKO,<br/>
- visualize the final layout of the four disks.



##  Example of Results a=0.30 m , b=0.20m

![1 disk](image/disk1.png)

![2 disks](image/disk2.png)

![3 disks](image/disk3.png)

![4 disks](image/disk4.png)


## Author

**Luc Agbognisso, MSc student in Mathematical Sciences at AIMS Ghana.**