# Sales-Data-Analysis-Project
# combining all sales files together into a single csv file
import os
import pandas as pd

directory = r"C:\Users\LENOVO\Downloads\Pandas-Data-Science-Tasks-master\Pandas-Data-Science-Tasks-master\SalesAnalysis\Sales_Data"

files = [file for file in os.listdir(directory) if file.endswith('.csv')]

all_months_data = pd.DataFrame()

for file in files:
    file_path = os.path.join(directory, file)
    df = pd.read_csv(file_path)
    all_months_data = pd.concat([all_months_data, df])

all_months_data.to_csv("allcomb_data.csv", index=False)
