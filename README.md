# CodeAlpha-Task-2
Internship purpose 
CODE
# Hardcoded dictionary of stock prices
stock_prices = {
    "AAPL": 180,
    "TSLA": 250,
    "GOOGL": 140,
    "AMZN": 130,
    "MSFT": 300
}

def stock_tracker():
    portfolio = {}
    print("Welcome to the Stock Portfolio Tracker!")
    print("Available stocks:", ", ".join(stock_prices.keys()))
    print("Enter 'done' when you're finished.\n")

    # Collect user input
    while True:
        stock = input("Enter stock symbol (e.g., AAPL): ").upper()
        if stock == "DONE":
            break
        if stock not in stock_prices:
            print("Invalid stock symbol. Try again.")
            continue
        try:
            quantity = int(input(f"Enter quantity of {stock}: "))
            if stock in portfolio:
                portfolio[stock] += quantity
            else:
                portfolio[stock] = quantity
        except ValueError:
            print("Please enter a valid number.")

    # Calculate total investment
    total_investment = 0
    print("\nYour Portfolio:")
    for stock, qty in portfolio.items():
        price = stock_prices[stock]
        value = price * qty
        total_investment += value
        print(f"{stock}: {qty} shares x ${price} = ${value}")

    print(f"\nTotal Investment Value: ${total_investment}")

    # Optional: Save to file
    save = input("\nDo you want to save this portfolio to a file? (yes/no): ").lower()
    if save == "yes":
        with open("portfolio.txt", "w") as file:
            file.write("Your Portfolio:\n")
            for stock, qty in portfolio.items():
                price = stock_prices[stock]
                value = price * qty
                file.write(f"{stock}: {qty} shares x ${price} = ${value}\n")
            file.write(f"\nTotal Investment Value: ${total_investment}")
        print("Portfolio saved to 'portfolio.txt'.")

        result
        ![CodeAlpha task 2](https://github.com/user-attachments/assets/97cfadeb-83a3-4e7e-bf46-d456bfe1d05c)


# Run the tracker
stock_tracker()
