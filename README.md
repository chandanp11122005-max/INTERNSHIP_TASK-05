# INTERNSHIP_TASK-05
Exploratory Data Analysis (EDA) Code
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
# Load dataset
df = pd.read_csv(r"c:\Users\Admin\Downloads\titanic.csv")
# First look
df.head()
# Basic structure and info
df.info()
# Statistical summary
df.describe()
sns.countplot(x='Species', data=df)
plt.title("Species Count")
plt.show()
plt.hist(df['SepalLengthCm'], bins=20)
plt.title("Sepal Length Distribution")
plt.xlabel("Sepal Length (cm)")
plt.ylabel("Frequency")
plt.show()
sns.scatterplot(
 x='SepalLengthCm',
 y='PetalLengthCm',
 hue='Species',
 data=df
)
plt.title("Sepal Length vs Petal Length")
plt.show()
plt.figure(figsize=(8,6))
sns.heatmap(df.corr(numeric_only=True), annot=True, cmap='coolwarm')
plt.title("Correlation Matrix")
plt.show()
sns.pairplot(df.drop(columns=['Id']), hue='Species')
plt.show()
