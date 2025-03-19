def modify_content(content):
    # Example modification: Convert text to uppercase
    return content.upper()

def read_and_write_file(input_file, output_file):
    try:
        # Read the input file
        with open(input_file, 'r') as file:
            content = file.read()
        
        # Modify the content
        modified_content = modify_content(content)
        
        # Write the modified content to the output file
        with open(output_file, 'w') as file:
            file.write(modified_content)
        
        print(f"File successfully modified and saved as {output_file}")
    
    except FileNotFoundError:
        print(f"Error: The file '{input_file}' does not exist.")
    except IOError:
        print(f"Error: Could not read or write to the file.")

# Example usage
input_filename = 'input.txt'
output_filename = 'output.txt'
read_and_write_file(input_filename, output_filename)

#Error Handling Lab 
def read_file(filename):
    try:
        with open(filename, 'r') as file:
            content = file.read()
            print("File content:")
            print(content)
    except FileNotFoundError:
        print(f"Error: The file '{filename}' does not exist.")
    except PermissionError:
        print(f"Error: You do not have permission to read the file '{filename}'.")
    except IOError:
        print(f"Error: Could not read the file '{filename}'.")

# Ask the user for a filename
filename = input("Enter the filename to read: ")
read_file(filename)
