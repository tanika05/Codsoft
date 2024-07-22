#Codsoft
TASK-1 SIMPLE CALCULATOR

    def calculator():
      print("WELCOME TO THE CALCULATOR!")
      print("ENTER AN OPERATION:")
      print("1:+")
      print("2:-")
      print("3:*")
      print("4:/")

      operation=input("ENTER THE NUMBER OF THE OPERATION YOU WANT TO PERFORM:")
      num1=float(input("ENTER THE FIRST NUMBER:"))
      num2=float(input("ENTER THE SECOND NUMBER:"))
      if operation=='1':
        result=num1+num2
        print(f"THE RESULT OF {num1}+{num2} is:{result}")
      elif operation=='2':
        result=num1-num2
        print(f"THE RESULT OF {num1}-{num2} is:{result}")
      elif operation=='3':
        result=num1*num2
        print(f"THE RESULT OF{num1}*{num2} is:{result}")
      elif operation=='4':
        if num2!=0:
            result=num1/num2
            print(f"THE RESULT OF{num1}/{num2} is:{result}")
        else:
            print("ERROR")
      else:
         print("invalid operation choice")

    calculator()

TASK-2 PASSWORD GENERATOR

    import random
    import string

    def generate_password(length):
    #Define possible characters: uppercase, lowercase, digits, and special characters
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

TASK-3 STONE,PAPER AND SCISSORS GAME

    import random
    def get_user_choice():
      choices = ["rock", "paper", "scissors"]
      user_choice = input("Enter your choice (rock, paper, or scissors): ").lower()
      while user_choice not in choices:
        print("Invalid choice. Please try again.")
        user_choice = input("Enter your choice (rock, paper, or scissors): ").lower()
      return user_choice

    def get_computer_choice():
     choices = ["rock", "paper", "scissors"]
     return random.choice(choices)

    def determine_winner(user_choice, computer_choice):
      if user_choice == computer_choice:
        return "tie"
      elif (user_choice == "rock" and computer_choice == "scissors") or \
         (user_choice == "scissors" and computer_choice == "paper") or \
         (user_choice == "paper" and computer_choice == "rock"):
        return "user"
      else:
        return "computer"

    def display_result(user_choice, computer_choice, winner):
      print(f"\nYou chose: {user_choice}")
      print(f"Computer chose: {computer_choice}")
      if winner == "tie":
        print("It's a tie!")
      elif winner == "user":
        print("You win!")
      else:
        print("Computer wins!")

    def main():
      user_score = 0
      computer_score = 0

      while True:
        user_choice = get_user_choice()
        computer_choice = get_computer_choice()
        winner = determine_winner(user_choice, computer_choice)
        
        display_result(user_choice, computer_choice, winner)
        
        if winner == "user":
            user_score += 1
        elif winner == "computer":
            computer_score += 1
        
        print(f"\nScore - You: {user_score}, Computer: {computer_score}")
        
        play_again = input("\nDo you want to play again? (yes/no): ").lower()
        if play_again != "yes":
            break

    print("\nThank you for playing! Final Score - You: {}, Computer: {}".format(user_score, computer_score))
    
    if __name__ == "__main__":
    main()
