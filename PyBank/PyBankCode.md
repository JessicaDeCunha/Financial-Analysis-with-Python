# PyBank Solution

# Import necessary dependencies

import os
import csv

# create the path for the file name

budget_data = os.path.join("/Users/jessicarosedecunhacarmichael/Desktop/Important stuff/UofT FinTech/FinTech Class Repo/utor-tor-fin-pt-05-2020-u-c/02-Python/Homework/Instructions/PyBank/Resources", "budget_data.csv")

# Write data to a .csv file

with open(budget_data, newline="") as csvfile:
    csvreader = csv.reader(csvfile, delimiter=",")
    csv_header = next(csvfile)
    
# Skip header

    print(f"Header: {csv_header}")

# Find profit and loss

    P = []
    months = []


# Loop through list on .csv

    for rows in csvreader:
        P.append(int(rows[1]))
        months.append(rows[0])


# Calculate change in revenue
    revenue_change = []

    for x in range(1, len(P)):
        revenue_change.append((int(P[x]) - int(P[x-1])))
    
    
# Calculate average revenue change
    revenue_average = sum(revenue_change) / len(revenue_change)
   
   
# Calculate total length of months in list
    total_months = len(months)


# Greatest increase in revenue
    greatest_increase = max(revenue_change)
    
    
# Greatest decrease in revenue
    greatest_decrease = min(revenue_change)



# Print the Results
    print("Financial Analysis")

    print("....................................................................................")

    print("total months: " + str(total_months))

    print("Total: " + "$" + str(sum(P)))

    print("Average change: " + "$" + str(revenue_average))

    print("Greatest Increase in Profits: " + str(months[revenue_change.index(max(revenue_change))+1]) + " " + "$" + str(greatest_increase))

    print("Greatest Decrease in Profits: " + str(months[revenue_change.index(min(revenue_change))+1]) + " " + "$" + str(greatest_decrease))


#output to a text file

    file = open("output.txt","w")

    file.write("Financial Analysis" + "\n")

    file.write("........................................................................." + "\n")

    file.write("total months: " + str(total_months) + "\n")

    file.write("Total: " + "$" + str(sum(P)) + "\n")

    file.write("Average change: " + "$" + str(revenue_average) + "\n")

    file.write("Greatest Increase in Profits: " + str(months[revenue_change.index(max(revenue_change))+1]) + " " + "$" + str(greatest_increase) + "\n")

    file.write("Greatest Decrease in Profits: " + str(months[revenue_change.index(min(revenue_change))+1]) + " " + "$" + str(greatest_decrease) + "\n")

    file.close()


