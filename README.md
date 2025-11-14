<h1 align="center">Hi, I'm Kim Aeriel 👋</h1>

---

<p align="center">
  <em>💻 Computer Science Student | ⚡ Problem Solver | 🌱 Always Learning</em>
</p>

<p align="center">
  <a href="mailto:your.email@example.com" title="Email">
    <img alt="email" src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white"/>
  </a>
  <a href="https://www.linkedin.com/in/your-linkedin" title="LinkedIn">
    <img alt="linkedin" src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>
  </a>
  <a href="https://github.com/your-github" title="GitHub">
    <img alt="github" src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white"/>
  </a>
</p>

---

### 🎓 Education

- **Bachelor of Science in Computer Science**
  - [New Era University] (2024 – Present)

---

### 📜 Certificates

| Certificate | Issued By | Year |
|---|---:|---:|
| [Introduction to Cybersecurity](https://drive.google.com/file/d/1pYepQ4Q4aguL3iDqsbrg-kimREEIAFQX/view?usp=sharing) | Cisco Net Acad | 2025 |
| [SQL Database 101](https://drive.google.com/file/d/1TqRAgKz5aN1TlBJ-QkI9A-omdJ8-9Esk/view?usp=sharing) | Cognitive Class AI | 2025 |

### 🛠 Skills

- **Programming Languages:** Java, SQL, Python, HTML, CSS, TypeScript, JavaScript, Shell  
- **Databases & Services:** IBM DB2 Cloud, Supabase, MongoDB  
- **Frameworks & Tools:** React, Node.js, Lucidchart, Figma, Canva Education, Notion  
- **Dev Tools:** Visual Studio Code, Google Workspace, Git, Microsoft Office, Vercel, Heroku

<p align="center">
  <!-- Tech icons row: replace or remove as desired -->
  <img alt="js" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" />
  <img alt="ts" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" />
  <img alt="react" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original.svg" />
  <img alt="node" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original.svg" />
  <img alt="mongodb" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original.svg" />
  <img alt="python" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" />
  <img alt="java" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" />
  <img alt="vscode" height="36" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vscode/vscode-original.svg" />
</p>

---

import random
import os

class NumberGuessingGame:
    def __init__(self):
        self.score = 0
        self.high_score = 0
        self.load_high_score()
    
    def load_high_score(self):
        """Load high score from file if it exists"""
        try:
            if os.path.exists("high_score.txt"):
                with open("high_score.txt", "r") as file:
                    self.high_score = int(file.read())
        except:
            self.high_score = 0
    
    def save_high_score(self):
        """Save high score to file"""
        with open("high_score.txt", "w") as file:
            file.write(str(self.high_score))
    
    def display_menu(self):
        """Display the main menu"""
        print("\n" + "="*40)
        print("      🎯 NUMBER GUESSING GAME 🎯")
        print("="*40)
        print(f"🏆 Current High Score: {self.high_score}")
        print("1. Start Game")
        print("2. How to Play")
        print("3. Exit")
        print("="*40)
    
    def display_instructions(self):
        """Display game instructions"""
        print("\n📖 HOW TO PLAY:")
        print("• I'm thinking of a number between 1-100")
        print("• You have to guess the correct number")
        print("• I'll tell you if your guess is too high or too low")
        print("• Try to guess in as few attempts as possible!")
        print("• Lower attempts = Higher score!")
        input("\nPress Enter to return to menu...")
    
    def play_game(self):
        """Main game logic"""
        number_to_guess = random.randint(1, 100)
        attempts = 0
        max_attempts = 10
        
        print(f"\n🎮 I'm thinking of a number between 1 and 100!")
        print(f"You have {max_attempts} attempts to guess it!")
        
        while attempts < max_attempts:
            attempts += 1
            remaining_attempts = max_attempts - attempts + 1
            
            try:
                guess = int(input(f"\n🔢 Attempt {attempts}/{max_attempts} - Enter your guess: "))
            except ValueError:
                print("❌ Please enter a valid number!")
                attempts -= 1
                continue
            
            if guess < 1 or guess > 100:
                print("❌ Please enter a number between 1 and 100!")
                attempts -= 1
                continue
            
            if guess == number_to_guess:
                score = max(1, (max_attempts - attempts + 1) * 10)
                self.score += score
                print(f"\n🎉 CONGRATULATIONS! You guessed it!")
                print(f"💡 The number was: {number_to_guess}")
                print(f"⭐ You took {attempts} attempts")
                print(f"💰 Score earned: +{score}")
                print(f"🏅 Total Score: {self.score}")
                
                if self.score > self.high_score:
                    self.high_score = self.score
                    self.save_high_score()
                    print("🔥 NEW HIGH SCORE! 🔥")
                break
            elif guess < number_to_guess:
                print(f"📈 Too low! ", end="")
            else:
                print(f"📉 Too high! ", end="")
            
            # Give hint after first few attempts
            if attempts >= 3:
                difference = abs(guess - number_to_guess)
                if difference <= 5:
                    print("You're very close! 🔥")
                elif difference <= 15:
                    print("You're getting warm! 🌡️")
                else:
                    print("You're quite cold! ❄️")
            else:
                print("Keep going!")
            
            print(f"💡 Attempts remaining: {remaining_attempts - 1}")
        
        else:
            print(f"\n💔 GAME OVER! You've used all {max_attempts} attempts!")
            print(f"💡 The number was: {number_to_guess}")
            print("Better luck next time!")
    
    def run(self):
        """Main game loop"""
        while True:
            self.display_menu()
            
            try:
                choice = input("\nEnter your choice (1-3): ").strip()
                
                if choice == "1":
                    self.play_game()
                    input("\nPress Enter to continue...")
                elif choice == "2":
                    self.display_instructions()
                elif choice == "3":
                    print(f"\n🎊 Thanks for playing!")
                    print(f"💎 Final Score: {self.score}")
                    print(f"🏆 High Score: {self.high_score}")
                    print("👋 Goodbye!")
                    break
                else:
                    print("❌ Invalid choice! Please enter 1, 2, or 3.")
            except KeyboardInterrupt:
                print("\n\n👋 Game interrupted. Thanks for playing!")
                break

# Run the game
if __name__ == "__main__":
    game = NumberGuessingGame()
    game.run()
