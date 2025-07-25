Here is a list of basic Linux commands:

pwd

ls

cd

mkdir

touch

mv

rm

cat

echo

chmod

clear

whoami

man

date

cal

uname

dfpwd

cp file1.txt file2.txt

→ Copies file1.txt to file2.txt.

cp -r folder1 folder2
→ Recursively copies folder1 (including contents) to folder2.


mv oldname.txt newname.txt

→ Renames the file.

mv file.txt /home/user/
→ Moves file.txt to /home/user/.


rm file.txt
→ Deletes the file file.txt.

rm -r foldername
→ Deletes the folder and its contents recursively.



---------------------------------
1) # This is a comment first program script.sh

echo "Hello, world!"  # Print a message

To run a script:

chmod +x script.sh     # Make it executable
./script.sh            # Run the script


2) ✅ Example 1: Print Hello World
bash
Copy
Edit
#!/bin/bash
echo "Hello, world!"



Example 2: Take Input and Greet
bash
Copy
Edit
#!/bin/bash
echo "Enter your name:"
read name
echo "Hello, $name!"



 Example 3: Check if a File Exists
bash
Copy
Edit
#!/bin/bash
echo "Enter filename:"
read file
if [ -f "$file" ]; then
  echo "File exists."
else
  echo "File does not exist."
fi




 Example 4: Sum of Two Numbers
bash
Copy
Edit
#!/bin/bash
echo "Enter two numbers:"
read a
read b
sum=$((a + b))
echo "Sum is: $sum"I

 Example 5: Loop through Numbers
bash
Copy
Edit
#!/bin/bash
for i in {1..5}
do
  echo "Number: $i"
done



 Example 6: Check Odd or Even
bash
Copy
Edit
#!/bin/bash
read -p "Enter a number: " num
if (( num % 2 == 0 )); then
  echo "$num is Even"
else
  echo "$num is Odd"
fi


 Example 7: Create Directory and Files
bash
Copy
Edit
#!/bin/bash
mkdir -p myfolder
touch myfolder/file1.txt myfolder/file2.txt
echo "Files created inside myfolder"



✅ Example 8: Find Factorial of a Number
bash
Copy
Edit
#!/bin/bash
read -p "Enter a number: " n
fact=1
for (( i=1; i<=n; i++ ))
do
  fact=$((fact * i))
done
echo "Factorial of $n is $fact"



Example 10: Display Current Date, Time, and Logged-In User
bash
Copy
Edit
#!/bin/bash
echo "Current date and time: $(date)"
echo "Logged in user: $(whoami)"


✅ Example 11: Count Number of Files in a Directory
bash
Copy
Edit
#!/bin/bash
read -p "Enter directory name: " dir
if [ -d "$dir" ]; then
  count=$(ls "$dir" | wc -l)
  echo "Total files in $dir: $count"
else
  echo "Directory does not exist."
fi



Example 14: Simple Menu-Driven Script
bash
Copy
Edit
#!/bin/bash
echo "1. Date"
echo "2. List Files"
echo "3. Who is logged in"
read -p "Enter your choice [1-3]: " choice

case $choice in
  1) date ;;
  2) ls -l ;;
  3) who ;;
  *) echo "Invalid choice" ;;
esac





i=1
while [ $i -le 5 ]
do
  echo "Number: $i"
  ((i++))
done



#!/bin/bash

# Prompt user to enter filename
echo -n "Enter the filename to read: "
read filename

# Check if the file exists
if [ -f "$filename" ]; then
    echo "Contents of $filename:"
    cat "$filename"
else
    echo "File '$filename' does not exist."
fi



1. Reverse the Digits of a Number
bash
Copy
Edit
#!/bin/bash

echo -n "Enter a number: "
read num
rev=0

while [ $num -gt 0 ]
do
    rem=$((num % 10))
    rev=$((rev * 10 + rem))
    num=$((num / 10))
done

echo "Reversed number: $rev"



Student Grading System
bash
Copy
Edit
#!/bin/bash

echo -n "Enter student's marks (0-100): "
read marks

if [ $marks -ge 90 ]; then
    echo "Grade: A"
elif [ $marks -ge 80 ]; then
    echo "Grade: B"
elif [ $marks -ge 70 ]; then
    echo "Grade: C"
elif [ $marks -ge 60 ]; then
    echo "Grade: D"
else
    echo "Grade: F (Fail)"
fi



 3. Sum of Digits of a Number
bash
Copy
Edit
#!/bin/bash

echo -n "Enter a number: "
read num
sum=0

while [ $num -gt 0 ]
do
    rem=$((num % 10))
    sum=$((sum + rem))
    num=$((num / 10))
done

echo "Sum of digits: $sum"

-----------------------------------------------------------------
calculator program

echo -n "Enter first number: "
read a
echo -n "Enter second number: "
read b
echo -n "Enter operator (+, -, *, /): "
read op

case $op in
    +) result=$((a + b));;
    -) result=$((a - b));;
    \*) result=$((a * b));;
    /) 
        if [ $b -ne 0 ]; then
            result=$((a / b))
        else
            echo "Error: Division by zero"
            exit 1
        fi
        ;;
    *) echo "Invalid operator"; exit 1;;
esac

echo "Result: $result


