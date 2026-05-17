# sports-analytics-portfolio 
import pandas as pd

# Mock data mapping Tilak Varma's real-world IPL match dates to his social metrics
# This showcases to RISE how you can automate brand metrics
data = {
    "Match_Date": ["2026-04-05", "2026-04-12", "2026-04-18", "2026-04-25"],
    "Opponent": ["RCB", "CSK", "KKR", "DC"],
    "Runs_Scored": [45, 84, 12, 61],
    "Instagram_Followers_Gain": [12000, 45000, 2000, 28000],
    "Sponsor_Post_Impressions": [150000, 420000, 95000, 310000]
}

df = pd.DataFrame(data)

# Calculate the conversion efficiency (Impressions generated per run scored)
df["Sponsor_ROI_Index"] = round(df["Sponsor_Post_Impressions"] / df["Runs_Scored"], 2)

# Export to CSV for Excel Dashboarding
df.to_csv("tilak_varma_brand_roi.csv", index=False)
print("Brand ROI analysis complete! Data exported to tilak_varma_brand_roi.csv")
