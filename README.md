# Higher Lower 

 **An age-old number guessing game.**  

This is my version of Higher/Lower, a Python-based game that engages the user in guessing a number within a range of 1-99.  

Higher/Lower is one of my first Python game programs. I wanted to write a simple number guessing game as a starter project and thought this would be a great opportunity for that.  
While looking for ideas on how to get started, I found a video on YouTube: [12 Beginner Python Projects](https://www.youtube.com/watch?v=8ext9G7xspg&t=886s).  
Check it out for your self. Code along with the presenter 6:55 mark.  

### What does the presenter's code do? ###
*The layout of the code in the video is as follows:*

```python
import random

def guess(x):
    random_number = random.randint(1, x)
    guess = 0
    while guess != random_number:
        guess = int(input(f'Guess a number between 1 and {x}: '))
        if guess < random_number:
            print('Sorry, guess again. Too low.')
        elif guess > random_number:
            print('Sorry, guess again. Too high.')

    print(f'Yay, congrats. You have guessed the number {random_number} correctly.')

guess(10)
```

### What does my code do differently? ###

I expanded on the code for this game from its straightforward nature to be a little more engaging with the user.  
A breakdown of this code includes:

1. **Welcoming message at the beginning of the game:**
```python
print('Welcome to Higher/Lower!')
print('Try your luck in this old guessing game!')
```

2. **Counter for guess attempts:**
```python
attempt_count += 1
```

3. **ValueError handling for incorrect input:**
```python
while True:
    attempt_count += 1
    try:
        guess = int(input(f'{"Guess a number between 1 and 99:" if attempt_count == 1 else "Guess another number:"} '))
    except ValueError:
        print("Invalid input. Please enter a valid number.")
        continue
```

4. **Instructions on user guess if too high or too low:**
```python
if guess < 1 or guess > 99:
    print(f'Attempt {attempt_count}: {guess} is out of the valid range (1-99). Please try again.')
elif guess < random_number:
    print(f'Attempt {attempt_count}: {guess} is too low. Try a higher number.')
elif guess > random_number:
    print(f'Attempt {attempt_count}: {guess} is too high. Try a lower number.')
else:
    print(f'Attempt {attempt_count}: Congrats, you guessed the number correctly: {random_number}')
    break
```

5. **After correct guess, a congrats message specific to attempt count:**
```python
if attempt_count <= 4:
    print("Wow! Look at you. Winner, winner, chicken dinner!")
elif attempt_count <= 7:
    print("Um. Good job, I guess? You can do better!")
elif attempt_count <= 9:
    print("At least you can say you figured it out. Finally!")
else:
    print("Were you even trying?")
```

6. **Option to play again with handling for unacceptable responses:**
```python
def main():
    while True:
        guess(99)
        while True:
            play_again = input("\nWould you like to try again? (y/n): ").strip().lower()
            if play_again == 'n':
                print("Ok! Try again another time!!!")
                return
            elif play_again == 'y':
                break
            else:
                print("That is not an acceptable response. Please try again.")
```

This was a great project for my beginner skill set, and I am working on many more projects to build and expand my experience in working with Python for game development.  
Try the code yourself and enjoy.  

