
# Simple To-Do List App

tasks = []

def show_menu():
    print("\n===== TO-DO LIST =====")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Delete Task")
    print("4. Exit")

def add_task():
    task = input("Enter your task: ")
    tasks.append(task)
    print("Task added!")

def view_tasks():
    if not tasks:
        print("No tasks in the list.")
    else:
        print("\nYour Tasks:")
        for i, task in enumerate(tasks, start=1):
            print(f"{i}. {task}")

def delete_task():
    view_tasks()
    if tasks:
        try:
            task_num = int(input("Enter task number to delete: "))
            removed = tasks.pop(task_num - 1)
            print(f"Task '{removed}' deleted.")
        except (IndexError, ValueError):
            print("Invalid task number!")

# Main loop
while True:
    show_menu()
    choice = input("Enter your choice: ")
    
    if choice == '1':
        add_task()
    elif choice == '2':
        view_tasks()
    elif choice == '3':
        delete_task()
    elif choice == '4':
        print("Exiting... Bye!")
        break
    else:
        print("Invalid choice! Please select from 1 to 4.")