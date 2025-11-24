---
title: Implementation
weight: 4
icon: terminal
---

You don't need expensive new software to implement ATF. You can start today with the tools you already use, like Jira, Linear, or GitHub Issues.

## Implementation Steps

### 1. Define Your Assets
Create a list of your key data assets. This could be a simple spreadsheet or a dedicated "Assets" project in your issue tracker.

### 2. Configure Your Issue Tracker
Add two custom fields to your issue tracker:

*   **Linked Asset ID:** A reference to the asset being modified.
*   **Task Type:** A dropdown with values: `Flow`, `Flowless`, `Ad Hoc`.

### 3. Link Tasks to Assets
Every time you create a ticket, ensure it is linked to an Asset and has a Task Type assigned.

## Quick Start Script

Here is a Python script to help you analyze your tasks if you export them to CSV:

```python
import pandas as pd

def analyze_tasks(csv_file):
    df = pd.read_csv(csv_file)
    
    # Group by Task Type
    type_counts = df['Task Type'].value_counts()
    print("Task Distribution:")
    print(type_counts)
    
    # Calculate "Rent" (Flowless tasks per Asset)
    rent = df[df['Task Type'] == 'Flowless'].groupby('Linked Asset ID').size()
    print("\nAsset Rent (Top 5):")
    print(rent.sort_values(ascending=False).head())

if __name__ == "__main__":
    analyze_tasks('tasks.csv')
```
