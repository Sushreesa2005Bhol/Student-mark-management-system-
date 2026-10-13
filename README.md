# Student-mark-management-system-
For students mark management 
students = {}

def add_student():
    name = input("Enter student name: ")
    marks = []
    for i in range(1, 4):
        mark = float(input(f"Enter marks for subject {i}: "))
        marks.append(mark)
    students[name] = marks
    print("Student added successfully!")

def show_all():
    if not students:
        print("No student records found.")
        return

    for name, marks in students.items():
        total = sum(marks)
        percentage = total / len(marks)
        print(name, "Marks:", marks,
              "Total:", total, "Percentage:", percentage, "%")

def show_topper():
    if not students:
        print("No student records found.")
        return

    topper = max(students, key=lambda name: sum(students[name]))
    print("Topper:", topper)
    print("Total marks:", sum(students[topper]))

while True:
    print("\n1. Add student marks")
    print("2. Show all students")
    print("3. Show topper")
    print("4. Exit")

    choice = input("Enter choice: ")

    if choice == "1":
        add_student()
    elif choice == "2":
        show_all()
    elif choice == "3":
        show_topper()
    elif choice == "4":
        break
    else:
        print("Invalid choice!")
