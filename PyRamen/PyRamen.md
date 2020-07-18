# PyRamen Solution

# Import Libraries

import os
import csv
from pathlib import Path

# Set file path

menu_filepath = Path("/Users/jessicarosedecunhacarmichael/Desktop/Important\ stuff/UofT\ FinTech/FinTech\ REPO/utor-tor-fin-pt-05-2020-u-c/02-Python/Homework/Instructions/PyRamen/Resources/menu_data.csv")

sales_filepath = Path("/Users/jessicarosedecunhacarmichael/Desktop/Important\ stuff/UofT\ FinTech/FinTech\ REPO/utor-tor-fin-pt-05-2020-u-c/02-Python/Homework/Instructions/PyRamen/Resources/sales_data.csv")


# Initialize list objects to hold data

menu = []
sales = []

# Read in menu data into menu list
            
        
menu_data = os.path.join("/Users/jessicarosedecunhacarmichael/Desktop/Important\ stuff/UofT\ FinTech/FinTech\ REPO/utor-tor-fin-pt-05-2020-u-c/02-Python/Homework/Instructions/PyRamen/Resources/menu_data.csv")   
        
with open(menu_filepath, 'r') as csvfile:
    csvreader = csv.reader(csvfile, delimiter = ',')
    csv_header = next(csvreader)

# Read in Sales data into the sales list

with open(sales_data, newline="") as csvfile:
    csvreader = csv.reader(csvfile, delimiter=",")
    csv_header = next(csvfile)
