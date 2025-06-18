# GpaPython
Simple GPA Calulator

print("Hi! This is a GPA Calculator")
grades={
    "F": 0.0,
    "D": 1.0,
    "D+": 1.3,
    "C-": 1.7,
    "C": 2.0,
    "C+": 2.3,
    "B-": 2.7,
    "B": 3,
    "B+": 3.3,
    "A-":3.7,
    "A":4
}
gpa = 0
total_pos_credits = 0

cl_amount = input("How many classes do you have? ")
cl_List = []
cl_grades = []

if not cl_amount.isdigit() or int(cl_amount) <= 0:
    print("Please enter a valid number of classes.")
    cl_amount = input("How many classes do you have? ")

for i in range(int(cl_amount)):
    c1 = input("What is your " + str(i+1) + " class?")
    cl_List.append(c1)
    g2 = input("What was your grade for " + cl_List[i] + "?")
    if g2 not in grades:
        print("Invalid grade entered. Please enter a valid grade.")
        g2 = input("What was your grade for " + cl_List[i] + "?")
    else:
        g2 = grades[g2]
    cl_grades.append(g2)
    c3= input("How many credits is " + cl_List[i] + "?")
    total_pos_credits += float(c3)
    cl_grades[i] *= float(c3)

gpa = sum(cl_grades)/ total_pos_credits

print("Your GPA is: " + str(gpa))
