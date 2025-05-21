# filehandling-assighnment
# File: file_read_write.py

def modify_content(content):
    # Example modification: convert to uppercase
    return content.upper()

filename = input("Enter the filename to read: ")

try:
    with open(filename, 'r') as infile:
        data = infile.read()
        modified = modify_content(data)
    new_filename = "modified_" + filename
    with open(new_filename, 'w') as outfile:
        outfile.write(modified)
    print(f"Modified content written to {new_filename}")
except FileNotFoundError:
    print("Error: The file does not exist.")
except IOError:
    print("Error: Could not read or write the file.")
