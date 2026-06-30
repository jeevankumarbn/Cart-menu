while True:
    menu()
    
    choice = int(input("Enter the choice :"))

    if choice == 1:
        
        items = input("Enter the name of an item to add:").lower()
        
        if items in store_items:
            qty = int(input("Enter the quantiny required: "))
            cart[items] =cart.get(items, 0) + qty
            print(f"{qty} {items}(s) added to cart.")
        else:
            print("Choosen item isnot available currently.")

    elif choice == 2:
        items = input("Enter the name of an item to be removed: ").lower()
        if items in store_items:
            qty = int(input("Enter the quantity of an item to be removed: "))

            if qty >= cart[items]:
                del cart[items]
                print(f"removed all {items}(s) from cart.")
            else:
                cart[items] -= qty
                print(f"Removed {qty} {items}(s) from cart.")
        else:
            print("Item not found!")

    elif choice == 3:
        total = sum(store_items[items] *qty for items, qty in cart . items())
        name = input("Enter your name: ")
        print("cart: ",cart)
        
        print(f"{name} your total price is {total}")

    elif choice == 4:
        print("Thanks for shopping❤️")
        break

    else:
        print("Invalid option🤔 Try again...")
