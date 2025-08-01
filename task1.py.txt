import pandas as pd
import matplotlib.pyplot as plt

# Sample data for India's 2022 age distribution
data = {
    'Age Group': ['0-14', '15-24', '25-54', '55-64', '65+'],
    'Male': [190_000_000, 140_000_000, 200_000_000, 60_000_000, 50_000_000],
    'Female': [180_000_000, 130_000_000, 190_000_000, 65_000_000, 55_000_000]
}

df = pd.DataFrame(data)

# Plotting
bar_width = 0.4
index = range(len(df))

plt.figure(figsize=(10,6))
plt.bar([i - bar_width/2 for i in index], df['Male'], width=bar_width, label='Male', color='blue')
plt.bar([i + bar_width/2 for i in index], df['Female'], width=bar_width, label='Female', color='pink')

plt.xticks(index, df['Age Group'])
plt.xlabel('Age Group')
plt.ylabel('Population')
plt.title("India's Population Distribution by Age and Gender in 2022")
plt.legend()
plt.tight_layout()
plt.show()
