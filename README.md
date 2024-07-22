#Codsoft
TASK-2 
    import random
    import string

    def generate_password(length):
    # Define possible characters: uppercase, lowercase, digits, and special characters
    characters = string.ascii_letters + string.digits + string.punctuation
    
    # Generate a random password using the specified characters and length
    password = ''.join(random.choice(characters) for _ in range(length))
    
    return password

    def main():
    try:
        # Prompt the user to specify the desired length of the password
        length = int(input("Enter the desired length of the password: "))
        
        # Ensure the length is a positive integer
        if length <= 0:
            raise ValueError("Length must be a positive integer.")
        
        # Generate the password
        password = generate_password(length)
        
        # Display the generated password
        print(f"Generated password: {password}")
        
    except ValueError as e:
        print(f"Invalid input: {e}")

    if __name__ == "__main__":
    main()
