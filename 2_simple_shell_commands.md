1. To check the default shell in your system
echo $0

2. to check the version of your os
cat /etc/os-release
o/p
    NAME="Ubuntu"
    VERSION="20.04.6 LTS (Focal Fossa)"
    ID=ubuntu
    ID_LIKE=debian
    PRETTY_NAME="Ubuntu 20.04.6 LTS"
    VERSION_ID="20.04"
    HOME_URL="https://www.ubuntu.com/"
    SUPPORT_URL="https://help.ubuntu.com/"
    BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
    PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
    VERSION_CODENAME=focal
    UBUNTU_CODENAME=focal


3. to check the user name
whoami

4. to check the diff shells supported in system
cat /etc/shells

O/P
    cat /etc/shells 
    # /etc/shells: valid login shells
    /bin/sh
    /bin/bash
    /usr/bin/bash
    /bin/rbash
    /usr/bin/rbash
    /bin/dash
    /usr/bin/dash
    /usr/bin/tmux
    /usr/bin/screen


5. To print the current directory you are in
pwd

6. to read the permissions of a file
ls -lh

7. Diff ways to run a script

1. ./script_name.sh
2. bash script_name.sh
3. /path_to_script/script_name.sh

8. How to add single line comment 

# This is a single line comment

9. How to add multi line comment

<<comment
This is
a multi line comment
comment

10. How to save command o/p into a variable
variable_name=$(command_name)

11. how to create a read only variable in shell script

readonly variable_name=variable_value

eg - readonly name="sapna"

Now no one can change the value again

12. How to create an array in shell script

array_1 = (1 2 3 4 "hello" 5.5)  # remember here elements are seperated via space not via comma
And array are not defined with square brackets, its defined using ()

13. how to print an element of an array

echo ${array_1[0]}

14. how to print all the elements of an array

echo ${array_1[*]}

15. how to print the last element of an array

echo ${array_1[-1]}

16. how to print the length of an array

echo ${#array_1[*]}

17. how to do slicing of an array

echo ${array_1[*]:which_index_to_start_from:from_that_index_how_many_values_u_want}

eg - say i want to start from 3rd index and print 2 values from there, like python here u dont give the start and end index, you give the start index and then how many values u want to print from the start index

echo ${array_1[*]:3:2}

18. How to add new values into an existing array

array_1+=(6 7 8)
this will add these elements in the last

array_1 will now look like : (1 2 3 4 "hello" 5.5 6 7 8)

19. How to create a associate-array(dict) in shell

declare -A dict1
dict1=(["Name"]="Sapna" ["age"]=23 ["city"]="Bangalore")

20. How to access values of a associate-array

echo "The value of dict1["Name"] is : ${dict1["Name"]}"

21. To print the length of the associate array

echo "The length of the associate array is : ${#dict1[*]}"

22. To print all the keys of a dict

echo "All the keys in the dictionary are : ${!dict1[*]}"

23. To print all the values of a dict

echo "All the values in the dictionary are : ${dict1[*]}"

24. How to create a string in a shell

string_1="helloe"

25. How to print the length of a string

length_str=${#string_1}

26. How to print the string in uppercase

echo "The string in uppercase is : ${string_1^^}"

27. How to print the string in lowercase

echo "The string in lowercase is : ${string_1,,}"

28. How to replace a string 

string_1="Hey this is Sapna"

new_str=${string_1/Sapna/Tanisha}

echo "The updated string is : $new_str"

29. How to do slicing 

slice_str=${string_1:12:16}

echo "The sliced string is : $slice_str"

30. How to take user input

read var_name

31. How to ask user for input

echo "Enter your name: "
read name

or instead of echo we could use

read -p "Enter your name: " name

32. Arithmetic operations in shell

a=10
b=2
let sum=$a+$b
let sub=$a-$b
let mul=$a*$b
let div=$a/$b
let expo=$a**$b
let floor_division=$a//$b
let mod=$a%$b

echo "The addition of a and b using let command is : $sum"
echo "The substraction of a and b using let command is : $sub"
echo "The multiplication of a and b using let command is : $mul"
echo "The division of a and b using let command is : $div"
echo "The exponential of a and b using let command is : $expo"
echo "The floor division of a and b using let command is : $floor_division"
echo "The modulus of a and b using let command is : $mod"

echo "The addition of a and b using (()) is : $((a+b))"
echo "The substraction of a and b using (()) is : $((a-b))"
echo "The multiplication of a and b using (()) is : $((a*b))"
echo "The division of a and b using (()) is : $((a/b))"
echo "The exponential of a and b using (()) is : $((a*b))"
echo "The floor division of a and b using (()) is : $((a//b))"
echo "The modulus of a and b using (()) is : $((a%b))"

33. How to write if-else in shell


read -p "Enter your marks: " marks

if [$marks -gt 30]
then
    echo "You have passed
else
    echo "You have failed
fi

34. How to use if-elif-else in shell

#!/bin/bash


read -p "Enter your marks: " marks

if [ $marks -ge 80 ]
then
    echo "You have passed with first division"
elif [ $marks -ge 60 ]
then
	echo "You have passed with second division"
elif [ $marks -ge 40 ]
then
	echo "You have passed with third division"
else
    echo "You have failed"
fi

35. Switch case in shell

echo "Enter a for date"
echo "Enter b for list the directories"
echo "Enter c for printing the current working directory"

read choice

case $choice in
    a)date;;
    b)ls;;
    c)pwd;;
    *)echo "Please enter a valid input"

esac

36. Logical AND Operator

#!/bin/bash

read -p "Enter your name: " name
read -p "ENter your age: " age
read -p "Enter your nationality: " nationality


if [[ $age -ge 18 && $nationality == "Indian" ]]
then
        echo "$name can vote"
else
        echo "Sorry $name you can't vote"
fi

37. Logical OR Operator

#!/bin/bash


read -p "Enter a number: " num

if (( $num % 3 == 0 || $num % 5 == 0 ))
then
        echo "$num is divisible by 3 or 5"
else
        echo "$num is not divisible by 3 or 5"
fi

38. How to use logical and and or together

#!/bin/bash


echo "Learning how to use && and || together"


read -p "Enter your username: " username
read -sp "Enter your password: " password

if [[ ( $username == "Sapna" && $password == "sapna123" ) || $username == "root" || $username == "admin" ]]
then
        echo "You have logged in successfully"
else
        echo "Oops login failed"

fi

39. For loop 

#!/bin/bash


array_1=(1 2 3 4 5 6 7 8 9 10)
length_array=${#array_1[*]}


for (( i=0; i <= length_array; i++))
do
        echo ${array_1[i]}
done
echo "Using for in"

for i in ${array_1[@]}
do
        echo $i
done

40. for with file operations

#!/bin/bash

File_to_search="/home/hza1kor/Shell_scripting/text_files/names.txt"

for name in $(cat $File_to_search)
do

        echo "Name is $name"
done

41. Shell scripting

#!/bin/bash

read -p "Enter a number: " num
i=0

while (( $i <= num))
do
        echo $i
        ((i++))
done

42. How to use until loop

#!/bin/bash

read -p "Enter a number other than 2: " num

until [[ $num == 2 ]]
do
        echo $num
        ((num--))
done

43. How to create infinite loop using while 

#!/bin/bash

while true
do
        echo "Hii how are you"
        sleep 2s

done


44. How to read file content using while

#!/bin/bash

file_path="/home/hza1kor/Shell_scripting/text_files/names.txt"


while read file
do
        echo "THe name is $file"
done < $file_path


45. How to write a function in shell

#!/bin/bash

function Welcome {
        echo "Welcome to the page"
}

End () {
        echo "End of the page"
}

Welcome
echo "This is the middle part"
End

45. How to pass arguments to a function

#!/bin/bash


function add {
        num1=$1
        num2=$2
        sum=$num1_$num2
        echo "The sum of $num1 and $num2 is : $sum"
}
add 20 30








