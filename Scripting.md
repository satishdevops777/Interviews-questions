
# SHELL SCRIPTING

1. What is a shell script?
```
Answer: A shell script is a text file containing commands that run in a Unix/Linux shell.
```
2. How do you create and execute a shell script?
```
Answer:
nano script.sh
chmod +x script.sh
./script.sh
```
3. What is the difference between " and ' in shell scripting?
```
Answer: " " allows variable expansion, while ' ' treats everything as a literal string.
```
4. What is the purpose of set -e in shell scripts?
```
Answer: It stops execution if any command fails.
```
5. How do you define and use functions in shell scripting?
```
Answer:
function say_hello() {
    echo "Hello, $1!"
}
say_hello "User"
```
6. Coding Task Write a shell script to check if a given number is even or odd.
```
#!/bin/bash
echo "Enter a number:"
read num
if (( num % 2 == 0 )); then
    echo "Even"
else
    echo "Odd"
fi
```
