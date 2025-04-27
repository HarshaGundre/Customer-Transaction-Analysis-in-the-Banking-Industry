import pandas as pd
import matplotlib.pyplot as plt

# Load transaction data from a CSV file
# Make sure you have a CSV file named 'transactions.csv' with appropriate columns
data = pd.read_csv('transactions.csv')

# Display the first few rows of the dataset
print("Sample Data:")
print(data.head())

# Basic statistics of the dataset
print("\nDataset Overview:")
print(data.describe())

# Analyze high-value transactions
high_value_threshold = 100000  # Define your threshold
high_value_transactions = data[data['Amount'] > high_value_threshold]

print("\nHigh-Value Transactions:")
print(high_value_transactions)

# Analyze customer spending patterns
customer_summary = data.groupby('CustomerID').agg(
    Total_Spending=('Amount', 'sum'),
    Avg_Spending=('Amount', 'mean'),
    Transaction_Count=('Amount', 'count')
).reset_index()

print("\nCustomer Summary:")
print(customer_summary)

# Visualize customer spending distribution
plt.figure(figsize=(10, 6))
plt.hist(data['Amount'], bins=50, color='blue', alpha=0.7)
plt.xlabel('Transaction Amount')
plt.ylabel('Frequency')
plt.title('Distribution of Transaction Amounts')
plt.show()

# Save analyzed data to a new CSV file
customer_summary.to_csv('customer_summary.csv', index=False)
print("\nCustomer summary saved as 'customer_summary.csv'")
