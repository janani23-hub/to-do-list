# A basic to-do list program in Python

def show_menu():
    print("\n--- To-Do List Menu ---")
    print("1. View Tasks")
    print("2. Add Task")
    print("3. Remove Task")
    print("4. Exit")

def view_tasks(tasks):
    if not tasks:
        print("\nYour to-do list is empty!")
    else:
        print("\nYour To-Do List:")
        for i, task in enumerate(tasks, 1):
            print(f"{i}. {task}")

def add_task(tasks):
    new_task = input("\nEnter the task to add: ")
    tasks.append(new_task)
    print(f"Task added: {new_task}")

def remove_task(tasks):
    if not tasks:
        print("\nYour to-do list is empty!")
    else:
        view_tasks(tasks)
        try:
            task_num = int(input("\nEnter the number of the task to remove: "))
            removed_task = tasks.pop(task_num - 1)
            print(f"Task removed: {removed_task}")
        except (ValueError, IndexError):
            print("Invalid input. Please try again.")

def main():
    tasks = []
    while True:
        show_menu()
        choice = input("\nChoose an option (1-4): ")
        if choice == "1":
            view_tasks(tasks)
        elif choice == "2":
            add_task(tasks)
        elif choice == "3":
            remove_task(tasks)
        elif choice == "4":
            print("\nExiting To-Do List. Goodbye!")
            break
        else:
            print("Invalid choice. Please select a valid option.")

if __name__ == "__main__":
    main()
