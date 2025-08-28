# file-read

def read_and_modify_file():
    """
    Reads a file, modifies its content, and writes to a new file.
    Handles various file-related errors.
    """
    try:
        # Ask user for the filename
        filename = input("Enter the filename to read: ")
        
        # Read the original file
        with open(filename, 'r') as file:
            content = file.read()
        
        print(f"Successfully read from '{filename}'")
        
        # Modify the content (convert to uppercase in this example)
        modified_content = content.upper()
        
        # Ask user for output filename
        output_filename = input("Enter the output filename: ")
        
        # Write modified content to new file
        with open(output_filename, 'w') as file:
            file.write(modified_content)
        
        print(f"Successfully wrote modified content to '{output_filename}'")
        print(f"Original file had {len(content)} characters")
        print(f"New file has {len(modified_content)} characters")
        
    except FileNotFoundError:
        print(f"Error: The file '{filename}' was not found.")
        print("Please check the filename and try again.")
    
    except PermissionError:
        print(f"Error: Permission denied to read '{filename}'.")
        print("You might not have the necessary permissions.")
    
    except IsADirectoryError:
        print(f"Error: '{filename}' is a directory, not a file.")
    
    except UnicodeDecodeError:
        print(f"Error: Could not decode the file '{filename}'.")
        print("The file might be in a different encoding or binary format.")
    
    except IOError as e:
        print(f"Error: An I/O error occurred: {e}")
    
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Run the program
if __name__ == "__main__":
    print("File Read & Write Program")
    print("=========================")
    read_and_modify_file()

Example usage

File Read & Write Program
=========================
Enter the filename to read: example.txt
Successfully read from 'example.txt'
Enter the output filename: modified_example.txt
Successfully wrote modified content to 'modified_example.txt'
Original file had 150 characters
New file has 150 characters


error example


File Read & Write Program
=========================
Enter the filename to read: nonexistent.txt
Error: The file 'nonexistent.txt' was not found.
Please check the filename and try again.





    kkk
