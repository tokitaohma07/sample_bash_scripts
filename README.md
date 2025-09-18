# Sample_bash_scripts
practicing bash scripts


🔹 Example 1: Ask for age
```
#!/bin/bash
# age.sh
echo "Enter your age:"
read AGE
echo "You are $AGE years old!"
```


🔹 Example 2: Favorite color
```
#!/bin/bash
# color.sh
echo "What is your favorite color?"
read COLOR
echo "Wow! $COLOR is a beautiful color!"
```


🔹 Example 3: Add two numbers
```
#!/bin/bash
# add.sh
echo "Enter first number:"
read A
echo "Enter second number:"
read B
SUM=$((A + B))
echo "The sum of $A and $B is $SUM"
```


🔹 Example 4: Guess the secret number
```
#!/bin/bash
# guess.sh
SECRET=7
echo "Guess a number between 1 and 10:"
read GUESS
if [ "$GUESS" -eq "$SECRET" ]; then
  echo "Correct! 🎉"
else
  echo "Oops! The secret number was $SECRET"
fi
```


🔹 Example 5: Today’s date
```
#!/bin/bash
# date.sh
echo "Today is: $(date)"
```
