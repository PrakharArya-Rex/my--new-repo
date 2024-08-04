# my--new-repo
connecting-vscode to github
1. Find whether the given number is even or odd
sh
Copy code
#!/bin/bash

echo "Enter a number:"
read num

if [ $((num % 2)) -eq 0 ]; then
    echo "$num is even."
else
    echo "$num is odd."
fi
2. Print the first 'n' odd numbers
sh
Copy code
#!/bin/bash

echo "Enter the value of n:"
read n

count=0
num=1

while [ $count -lt $n ]
do
    echo $num
    num=$((num + 2))
    count=$((count + 1))
done
3. Find all the possible quadratic equation roots using case
sh
Copy code
#!/bin/bash

echo "Enter coefficients a, b and c:"
read a b c

discriminant=$((b*b - 4*a*c))

case $discriminant in
    0)
        root=$((-b / (2*a)))
        echo "Roots are equal and the root is $root."
        ;;
    -*)
        realPart=$((-b / (2*a)))
        imagPart=$((sqrt(-discriminant) / (2*a)))
        echo "Roots are imaginary and they are $realPart + i$imagPart and $realPart - i$imagPart."
        ;;
    *)
        root1=$(( (-b + sqrt(discriminant)) / (2*a) ))
        root2=$(( (-b - sqrt(discriminant)) / (2*a) ))
        echo "Roots are real and they are $root1 and $root2."
        ;;
esac
4. Find the factorial of a given number
sh
Copy code
#!/bin/bash

echo "Enter a number:"
read num

factorial=1

for (( i=1; i<=num; i++ ))
do
  factorial=$((factorial * i))
done

echo "Factorial of $num is $factorial."
Additional Exercises
i) Find whether the given string is a palindrome
sh
Copy code
#!/bin/bash

echo "Enter a string:"
read str

rev=$(echo $str | rev)

if [ "$str" == "$rev" ]; then
    echo "$str is a palindrome."
else
    echo "$str is not a palindrome."
fi
ii) Find out the sum of the numbers given by the user
sh
Copy code
#!/bin/bash

echo "Enter numbers separated by space:"
read -a numbers

sum=0

for num in "${numbers[@]}"
do
    sum=$((sum + num))
done

echo "The sum of the numbers is $sum."
These scripts can be run in a Unix/Linux shell environment. Make sure to give execute permissions to the scripts using the chmod +x filename.sh command before running them.
