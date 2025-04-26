# week-4-plp-python
# File Read & Write Challenge + Error Handling Lab

def main():
    # Ask user for the input filename
    input_filename = input("Enter the name of the file to read: ")

    try:
        # Try to open and read the input file
        with open(input_filename, 'r') as infile:
            content = infile.read()

        # Modify the content (for example, convert to uppercase)
        modified_content = content.upper()

        # Prepare the output filename
        output_filename = f"modified_{input_filename}"

        # Write the modified content to the new file
        with open(output_filename, 'w') as outfile:
            outfile.write(modified_content)

        print(f"File successfully read and modified content saved to '{output_filename}'.")

    except FileNotFoundError:
        print(f"Error: The file '{input_filename}' does not exist.")
    except IOError:
        print(f"Error: The file '{input_filename}' could not be read.")

if __name__ == "__main__":
    main()
