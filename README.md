# Employee-Profile
# PYTHON CODE

# In this script
The dataset is loaded using pandas.
The get_employee_details function filters the dataset for the provided employee names using the isin method.
The details of the specified employees are returned as a DataFrame.

 loading  the data and write the function in the current environment. 

# In this script
The dataset is loaded using pandas.
The get_employee_details function filters the dataset for the provided employee names using the isin method.
The details of the specified employees are returned as a DataFrame.


We create a dictionary data_dict where each key is an employee's name, and the value is another dictionary with the employee's details.
The get_employee_details function searches for each employee name in the dictionary and returns their details. If an employee name is not found, it returns "Employee not found".

# Explanation of Error Handling
Type Checking:

We check if the employee_names parameter is a list. If not, a TypeError is raised.
We also check if each name in the employee_names list is a string. If not, a TypeError is raised.
Key Checking:

For each employee name in the list, we check if it exists in the data_dict. If an employee name is not found, we return "Employee not found" for that name.
Try-Except Block:

We wrap the example usage in a try-except block to catch and handle any exceptions that might occur, providing a user-friendly error message.


import pandas as pd

# Load the dataset
file_path = "C:\dataset\Total1.csv"  
data = pd.read_csv(file_path)

def get_employee_details(employee_names, data):
    """
    This function accepts a list of employee names and returns their details from the dataset.
    
    Parameters:
    employee_names (list): List of employee names to search for.
    data (DataFrame): The dataset containing employee details.
    
    Returns:
    DataFrame: A DataFrame containing the details of the specified employees.
    """
    # Filter the data for the specified employee names
    result = data[data['EmployeeName'].isin(employee_names)]
    return result

# Query usage
employee_names = ["NATHANIEL FORD", "GARY JIMENEZ"]
details = get_employee_details(employee_names, data)
print(details)

Creating a dictionary data_dict where each key is an employee's name, and the value is another dictionary with the employee's details.
The get_employee_details function searches for each employee name in the dictionary and returns their details. If an employee name is not found, it returns "Employee not found".

# Explanation of Error Handling:
Type Checking:
We check if the employee_names parameter is a list. If not, a TypeError is raised.
We also check if each name in the employee_names list is a string. If not, a TypeError is raised.
Key Checking:

For each employee name in the list, we check if it exists in the data_dict. If an employee name is not found, we return "Employee not found" for that name.
Try-Except Block:

We wrap the example usage in a try-except block to catch and handle any exceptions that might occur, providing a user-friendly error message.
This implementation ensures that the function handles invalid inputs gracefully and provides meaningful error messages when something goes wrong.

Explanation:
Data Preparation
The data_dict dictionary contains employee details.
Function Definition:

The export_employee_to_csv function takes an employee name, the data dictionary, and an optional output directory.
It checks if the employee exists in the dictionary. If not, it prints an error message.
It creates the output directory if it does not exist.
It writes the employee's details to a CSV file named after the employee (spaces replaced with underscores).
It creates a zip file in the specified output directory and adds the CSV file to it.
It removes the temporary CSV file after adding it to the zip file.
Example Usage:

The function is called with the name "NATHANIEL FORD" to demonstrate its usage.
This script ensures that the employee's details are exported to a CSV file and saved in a zipped folder named "Employee Profile". You can call the function with different employee names as needed.


# R CODE
Unzip and Display CSV Data
This project contains an R script that unzips a specified folder and displays the data from CSV files within that folder. The script ensures that the extraction directory exists, extracts the contents of the zip file, and reads and prints the data from any CSV files found.

Requirements
R (version 3.6 or higher)
The utils package (included with base R)
Usage
Download or Clone the Repository

Download the ZIP file containing the project or clone the repository using Git.

Prepare Your Files

Ensure you have a zip file containing the CSV files you want to extract and display. Place the zip file in the appropriate directory.

Run the R Script

Open your R environment (RStudio or any other R interface) and run the provided R script. You need to specify the path to your zip file and the extraction directory.

Example Usage
r
Copy code
# Load necessary libraries
library(utils)

# Function to unzip and display data
unzip_and_display_data <- function(zip_file_path, extract_to_dir) {
  # Ensure the extraction directory exists
  if (!dir.exists(extract_to_dir)) {
    dir.create(extract_to_dir, recursive = TRUE)
  }
  
  # Unzip the file
  unzip(zip_file_path, exdir = extract_to_dir)
  
  # List the files in the extracted directory
  extracted_files <- list.files(extract_to_dir, full.names = TRUE)
  
  # Read and display the CSV file(s)
  for (file in extracted_files) {
    if (grepl("\\.csv$", file)) {
      df <- read.csv(file)
      print(paste("Contents of", file, ":"))
      print(df)
    }
  }
}

# Example usage
zip_file_path <- "Employee Profile/Employee Profile.zip"
extract_to_dir <- "Employee Profile/unzipped"

unzip_and_display_data(zip_file_path, extract_to_dir)
In this example:

zip_file_path is the path to your zip file.
extract_to_dir is the directory where you want to extract the contents.
Check the Output

The script will print the contents of each CSV file found in the extraction directory.

Notes
Ensure that the paths to the zip file and extraction directory are correct.
The script will create the extraction directory if it does not exist.
The script only reads and displays files with a .csv extension.
Troubleshooting
Directory Creation: If the extraction directory does not exist and cannot be created, check your directory permissions.
File Paths: Ensure that the file paths are correctly specified and that the zip file exists at the given location.
CSV Format: Ensure that the files in the zip archive have a .csv extension and are in a valid CSV format.
