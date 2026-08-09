# Pet Care Management System

pets = []

def add_pet():
    name = input("Enter pet name: ")
    pet_type = input("Enter pet type: ")
    age = input("Enter pet age: ")
    owner = input("Enter owner name: ")

    pet = {
        "name": name,
        "type": pet_type,
        "age": age,
        "owner": owner
    }

    pets.append(pet)
    print("Pet added successfully!")


def view_pets():
    if not pets:
        print("No pet records found.")
        return

    print("\n--- Pet Records ---")
    for i, pet in enumerate(pets, 1):
        print(f"\nPet {i}")
        print("Name  :", pet["name"])
        print("Type  :", pet["type"])
        print("Age   :", pet["age"])
        print("Owner :", pet["owner"])


def delete_pet():
    if not pets:
        print("No pet records found.")
        return

    view_pets()

    try:
        number = int(input("\nEnter pet number to delete: "))

        if 1 <= number <= len(pets):
            pets.pop(number - 1)
            print("Pet record deleted successfully!")
        else:
            print("Invalid pet number.")

    except ValueError:
        print("Please enter a valid number.")


while True:
    print("\n===== Pet Care Management System =====")
    print("1. Add Pet")
    print("2. View Pets")
    print("3. Delete Pet")
    print("4. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        add_pet()
    elif choice == "2":
        view_pets()
    elif choice == "3":
        delete_pet()
    elif choice == "4":
        print("Thank you!")
        break
    else:
        print("Invalid choice. Please try again.")
