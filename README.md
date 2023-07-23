# Doctervisits-analysis
import pandas as pd
import matplotlib.pyplot as plt

# Sample data (Replace this with your actual dataset)
data = pd.DataFrame({
    'Date': ['2023-07-01', '2023-07-02', '2023-07-03', '2023-07-04', '2023-07-05'],
    'Patient_ID': [1, 2, 3, 4, 5],
    'Diagnosis': ['Fever', 'Cough', 'Headache', 'Fever', 'Back Pain'],
    'Treatment': ['Antipyretics', 'Cough Syrup', 'Pain Relievers', 'Antipyretics', 'Physical Therapy'],
    'Doctor': ['Dr. Smith', 'Dr. Johnson', 'Dr. Lee', 'Dr. Smith', 'Dr. Miller']
})

# Data Preprocessing (Data loading and cleaning would be performed in real-world scenarios)
# Replace the above sample data loading with actual data loading from a CSV or other sources

# Descriptive Statistics
print("Descriptive Statistics:")
print(data.describe())

# Diagnosis Analysis
diagnosis_counts = data['Diagnosis'].value_counts()
print("\nDiagnosis Counts:")
print(diagnosis_counts)

# Patient Demographics
age_groups = pd.cut(data['Age'], bins=[0, 18, 30, 45, 60, 100], labels=['0-18', '19-30', '31-45', '46-60', '61+'])
age_group_counts = age_groups.value_counts()
print("\nAge Group Counts:")
print(age_group_counts)

# Visualization
# Example: Bar plot of diagnosis counts
plt.figure(figsize=(8, 6))
plt.bar(diagnosis_counts.index, diagnosis_counts.values)
plt.title("Diagnosis Counts")
plt.xlabel("Diagnosis")
plt.ylabel("Count")
plt.xticks(rotation=45)
plt.show()
