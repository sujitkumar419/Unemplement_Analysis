# Load dataset (make sure Unemployment.csv is in the same folder)
df = pd.read_csv("Unemployment.csv")

print("Dataset Shape:", df.shape)
df.head()

# Convert date column to datetime
df['Date'] = pd.to_datetime(df['Date'], errors='coerce')

# Check missing values
print("Missing values:\n", df.isnull().sum())

plt.figure(figsize=(12,6))
sns.lineplot(x="Date", y="UnemploymentRate", data=df)
plt.title("Unemployment Rate Over Time")
plt.xlabel("Year")
plt.ylabel("Unemployment Rate (%)")
plt.show()
# Highlight Covid period (2020-2021)
covid_period = df[(df['Date'] >= "2020-01-01") & (df['Date'] <= "2021-12-31")]

plt.figure(figsize=(12,6))
sns.lineplot(x="Date", y="UnemploymentRate", data=df, label="Overall Trend")
sns.lineplot(x="Date", y="UnemploymentRate", data=covid_period, color="red", label="Covid Period")
plt.title("Impact of Covid-19 on Unemployment")
plt.xlabel("Year")
plt.ylabel("Unemployment Rate (%)")
plt.legend()
plt.show()

if "Region" in df.columns:
    plt.figure(figsize=(12,6))
    sns.boxplot(x="Region", y="UnemploymentRate", data=df)
    plt.title("Regional Unemployment Comparison")
    plt.xticks(rotation=45)
    plt.show()

## Insights
- Unemployment shows seasonal variations.
- Significant spike observed during Covid‑19 (2020–2021).
- Recovery trend visible post‑Covid period.
- Regional differences can highlight policy needs.



