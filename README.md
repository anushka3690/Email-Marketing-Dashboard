# Email Marketing Campaign Analysis & Dashboard

This project analyzes the performance of an **email marketing campaign** using data from three CSV files — `opened`, `clicked`, and `details`. The goal was to clean, process, and combine the datasets, then visualize the results in an **interactive Excel dashboard** to find actionable insights.



## Data Preparation & Cleaning
1. **Anomaly Detection & Removal**  
   - Removed inconsistent records where an email was marked as `clicked` but not `opened`:
     ```python
     anomaly = (df['opened'] == 0) & (df['clicked'] == 1)
     df = df[~anomaly]
     ```

2. **Data Merging**  
   - Imported all three CSV files using **Pandas** and merged them into a single DataFrame.
   
3. **Exporting Clean Data**  
   - Saved the cleaned dataset to CSV:
     ```python
     df.to_csv("cleaned_data.csv", index=False)
     ```
   - Converted the CSV to **Excel format** for pivot table and dashboard creation.



## Dashboard Creation
- Created **Pivot Tables** in Excel to analyze key campaign metrics.
- Designed a **dashboard** with interactive filters, charts, and KPIs to quickly interpret results.



# Key Insights

This analysis revealed several key patterns influencing campaign performance:

### 1. Personalization vs. Cost
- **Personalized emails** have higher engagement rates than generic ones.
- However, personalization increases campaign costs — requiring a balance between engagement gains and budget.

### 2. Content Length Optimization
- **Shorter email content** drives higher engagement and is more cost-efficient than longer messages.

### 3. Optimal Send Timing
- **Weekday campaigns** outperform weekend ones, with higher engagement at lower costs.

### 4. Purchase History as a Predictor
- Customers with **more past purchases** are significantly more likely to engage.

### 5. Hourly Engagement Trends
- The **hour-of-send distribution** is left-skewed (most emails sent early in the day).  
  Skewness should be addressed via transformation to avoid misinterpretation.

### 6. Geographical Targeting
- Campaigns targeted at the **USA** perform best, followed by the **UK**.  
  Spain and France show comparatively lower engagement.


## 🚀 Future Improvements
- Apply statistical transformations to correct skewed time-based features.
- Use predictive modeling to forecast engagement.



## 📂 Files in Repository
- `email_opened_table.csv` – Record of emails opened
- `link_clicked_table.csv` – Record of emails clicked
- `email_table.csv` – Campaign details data
- `cleaned_data.csv` – Processed and cleaned dataset
- `cleaned_data_transformed.xlsx` – Interactive Excel dashboard
