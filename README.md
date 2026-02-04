,# OS-Linux-commands-Shell-scripting
Operating systems Lab exercise
# Linux commands-Shell scripting
Linux commands-Shell scripting

# AIM:
To practice Linux Commands and Shell Scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Execute the following commands

### Step 3:

Testing the commands for the desired output. 

# COMMANDS:
### Create the following files file1, file2 as follows:
cat > file1
```
Sanjai.s.j
jayalakshmi.s
saravan.d
^d
```
cat > file2
```
pooja.s.j
sri
mahalakshmi
rani
^d
```
### Display the content of the files
cat < file1
## OUTPUT
```
ajay
arya
sanjai
surya
```
cat < file2
## OUTPUT
```
avi 
anjana
kaviya
swetha
```
# Comparing Files
cmp file1 file2
## OUTPUT
```
file1 file2 differ: byte 2, line 1
```
comm file1 file2
 ## OUTPUT
```
ajay
arya
	avi
	anjana
	kaviya
sanjai
surya
	swetha
``` 
diff file1 file2
## OUTPUT
```
1,4c1,4
< ajay
< arya
< sanjai
< surya
---
> avi
> anjana
> kaviya
> swetha
```
#Filters

### Create the following files file11, file22 as follows:

cat > file11
```
Hello world
This is my world
^d
```
cat > file22
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
^d
```
cut -c1-3 file11
## OUTPUT
```
Hel
Thi
```
cut -d "|" -f 1 file22
## OUTPUT
```
1001 
1002 
1003 
````
cut -d "|" -f 2 file22
## OUTPUT
```
 Ram 
 tom 
 Jeo 
```
cat > newfile 
```
Hello world
hello world
^d
````
cat < newfile 
Hello world
hello world
 
grep Hello newfile 
## OUTPUT

<img width="136" height="25" alt="image" src="https://github.com/user-attachments/assets/b50013d4-44e7-483f-9d51-c5222c126e13" />


grep hello newfile 
## OUTPUT

<img width="136" height="25" alt="image" src="https://github.com/user-attachments/assets/b9493fc5-b39f-40ac-8761-799e1bbd1d90" />

grep -v hello newfile 
## OUTPUT
```
Hello world

```
cat newfile | grep -i "hello"
## OUTPUT

<img width="140" height="50" alt="image" src="https://github.com/user-attachments/assets/5adb7d9f-514b-4952-927d-b21ebeba3967" />


cat newfile | grep -i -c "hello"
## OUTPUT
```
2
```
grep -R ubuntu /etc
## OUTPUT

<img width="1283" height="623" alt="image" src="https://github.com/user-attachments/assets/a4678784-5a7e-4a3a-842e-e710f3484480" />


grep -w -n world newfile   
## OUTPUT

<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/0891e8fc-5999-410f-9aa4-a222d94bb4a6" />

cat < newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```

cat > newfile
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
 ```
egrep -w 'Hello|hello' newfile 
## OUTPUT

<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/4c5c9573-f268-43b2-ac06-335359c90695" />

egrep -w '(H|h)ello' newfile 
## OUTPUT

<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/810c8dcf-6e4d-46ef-9ed0-a6d4ab8aabd3" />

egrep -w '(H|h)ell[a-z]' newfile 
## OUTPUT

<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/54913ea1-89e2-413f-9efc-a35164ac7f49" />


egrep '(^hello)' newfile 
## OUTPUT

<img width="161" height="28" alt="image" src="https://github.com/user-attachments/assets/a3320be5-d44a-4adb-b432-24d33952f08a" />

egrep '(world$)' newfile 
## OUTPUT

<img width="162" height="44" alt="image" src="https://github.com/user-attachments/assets/db5123e3-73f7-45c6-b105-a92611a6313d" />


egrep '(World$)' newfile 
## OUTPUT

<img width="162" height="44" alt="image" src="https://github.com/user-attachments/assets/ddac6d2b-31d3-4534-8ce9-2d3fd0dc140a" />

egrep '((W|w)orld$)' newfile 
## OUTPUT

<img width="316" height="69" alt="image" src="https://github.com/user-attachments/assets/b2c46535-4b5a-458c-ae1e-f604da739bff" />

egrep '[1-9]' newfile 
## OUTPUT

<img width="317" height="28" alt="image" src="https://github.com/user-attachments/assets/bb28c610-4e07-4b6d-96ce-81f6ece3a4dd" />

egrep 'Linux.*world' newfile 
## OUTPUT

<img width="317" height="28" alt="image" src="https://github.com/user-attachments/assets/94644706-cc4e-40f4-b5ab-85c304dc26aa" />

egrep 'Linux.*World' newfile 
## OUTPUT

<img width="317" height="28" alt="image" src="https://github.com/user-attachments/assets/a576e550-cecd-45a3-bda9-fda5dfb57eae" />

egrep l{2} newfile
## OUTPUT

<img width="315" height="48" alt="image" src="https://github.com/user-attachments/assets/10cc8e51-cb9a-406d-8d88-63713ea13cf7" />

egrep 's{1,2}' newfile
## OUTPUT 

<img width="378" height="92" alt="image" src="https://github.com/user-attachments/assets/a1ddfdbe-ab51-453c-a086-6204b5502d79" />

cat > file23
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
^d
```


sed -n -e '3p' file23
## OUTPUT
```
1002 | tom |  5000 | Admin
```
sed -n -e '$p' file23
## OUTPUT
```
1001 | Ram | 10000 | HR
```
sed  -e 's/Ram/Sita/' file23
## OUTPUT
```
1001 | Sita | 10000 | HR
1001 | Sita | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Sita | 10000 | HR
```
sed  -e '2s/Ram/Sita/' file23
## OUTPUT
```
1001 | Ram | 10000 | HR
1001 | Sita | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
```
sed  '/tom/s/5000/6000/' file23
## OUTPUT
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  6000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
```
sed -n -e '1,5p' file23
## OUTPUT
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
```
sed -n -e '2,/Joe/p' file23
## OUTPUT
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
```
sed -n -e '/tom/,/Joe/p' file23
## OUTPUT
```
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
```
seq 10 
## OUTPUT
```
1
2
3
4
5
6
7
8
9
10
```
seq 10 | sed -n '4,6p'
## OUTPUT
```
4
5
6
```
seq 10 | sed -n '2,~4p'
## OUTPUT
```
2
3
4
```
seq 3 | sed '2a hello'
## OUTPUT
```
1
2
hello
3
```
seq 2 | sed '2i hello'
## OUTPUT
```
1
hello
2
```
seq 10 | sed '2,9c hello'
## OUTPUT
```
1
hello
10
```
sed -n '2,4{s/^/$/;p}' file23
## OUTPUT
```
$1001 | Ram | 10000 | HR
$1001 | Ram | 10000 | HR
$1002 | tom |  5000 | Admin
```

#Sorting File content
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
sort file21
## OUTPUT
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1004 | Sit |  7000 | Dev
1005 | Sam |  5000 | HR
```
cat > file22
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
uniq file22
## OUTPUT
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
```
#Using tr command

cat file23 | tr [:lower:] [:upper:]
 ## OUTPUT
 ```
1001 | RAM | 10000 | HR
1001 | RAM | 10000 | HR
1002 | TOM |  5000 | ADMIN
1003 | JOE |  7000 | DEVELOPER
1005 | SAM |  5000 | HR
1004 | SIT |  7000 | DEV
1003 | JOE |  7000 | DEVELOPER
1001 | RAM | 10000 | HR
```

cat < urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```
cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
 ```
cat urllist.txt | tr -d ' '
 ## OUTPUT
```
www.yahoo.com
www.google.com
www.mrcet....com
```
cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT
```
www.yahoo.com
www.google.com
www.mrcet.com
```
#Backup commands
tar -cvf backup.tar *
## OUTPUT

<img width="946" height="1005" alt="Screenshot from 2026-02-04 13-34-27" src="https://github.com/user-attachments/assets/8b783589-4f43-4031-8fa0-ce74feec16f8" />


mkdir backupdir
 
mv backup.tar backupdir

cd backupdir
 
tar -tvf backup.tar
## OUTPUT

<img width="946" height="1005" alt="Screenshot from 2026-02-04 13-34-51" src="https://github.com/user-attachments/assets/5841ae6c-f642-4357-9018-5ce7dd2e8137" />

tar -xvf backup.tar
## OUTPUT
<img width="946" height="1005" alt="Screenshot from 2026-02-04 13-36-41" src="https://github.com/user-attachments/assets/8cc062c1-43a8-4be1-9ed7-99091d4f6b76" />

g
# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0 >> my-script.sh
```
chmod 755 my-script.sh
./my-script.sh
## OUTPUT

 
cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt
## OUTPUT

<img width="471" height="89" alt="image" src="https://github.com/user-attachments/assets/9839b223-0c25-4ad9-afc9-4d1d34394e70" />

cat < scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $1#
echo 'The $$ is ' $$
ps
^d
 ```

cat scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $\#
echo 'The $$ is ' $$
ps
```
 
chmod 777 scriptest.sh
 
./scriptest.sh 1 2 3

## OUTPUT

<img width="650" height="418" alt="image" src="https://github.com/user-attachments/assets/08df2649-66df-448b-bfe7-819e9d3e74db" />

ls file1
## OUTPUT
```
file1
```
o $?
## OUTPUT 
./one
bash: ./one: Permission denied

echo $?
 ## OUTPUT
```
127
```
# mis-using string comparisons

cat > strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
^d
```

cat strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
```
##OUTPUT

<img width="646" height="250" alt="image" src="https://github.com/user-attachments/assets/4f94634f-df0a-4602-9286-bcc1cd1fed6f" />

chmod 755 strcomp.sh
 
./strcomp.sh 

# check file ownership
cat < psswdperm.sh 
```bash
\#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
^d
```

cat psswdperm.sh 
```bash
/#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
 ```
./psswdperm.sh
## output:
<img width="450" height="35" alt="image" src="https://github.com/user-attachments/assets/cc43df81-7d6b-426e-9d6e-f88c9b566a53" />


# check if with file location
cat>ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```
cat ifnested.sh 
```
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

./ifnested.sh 
## OUTPUT
<img width="449" height="69" alt="image" src="https://github.com/user-attachments/assets/e3e6f126-3b73-46fc-a1b7-13c0ad488956" />

```
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```


# using numeric test comparisons
cat > iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
^d
```


cat iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
```

$ chmod 755 iftest.sh
 
$ ./iftest.sh 
## output:

<img width="448" height="40" alt="image" src="https://github.com/user-attachments/assets/757a4364-58a2-4d4d-81af-de3aa484d264" />

# check if a file
cat > ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```

cat ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

$ chmod 755 ifnested.sh
 
$ ./ifnested.sh 
##OUTPUT
<img width="359" height="63" alt="image" src="https://github.com/user-attachments/assets/ac0993e6-11a8-46d0-ae1b-9c08246e1585" />

# looking for a possible value using elif
cat elifcheck.sh 
```bash
\#!/bin/bash
if [ $USER = Ram ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Rahim ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Robert ]
then
echo "Special testing account"
elif [ $USER = gganesh ]
then
echo "$USER, Do not forget to logout when you're done"
else
echo "Sorry, you are not allowed here"
fi
```

$ chmod 755 elifcheck.sh
 
$ ./elifcheck.sh 
## OUTPUT

<img width="459" height="45" alt="image" src="https://github.com/user-attachments/assets/b50c63ae-537b-426d-8b17-21356f67042d" />

# testing compound comparisons
cat> ifcompound.sh 
```bash
\#!/bin/bash
if [ -d $HOME ] && [ -w $HOME ]
then
echo "The file exists and you can write to it"
else
echo "I cannot write to the file"
fi
```
$ chmod 755 ifcompound.sh
$ ./ifcompound.sh 
## OUTPUT

<img width="301" height="35" alt="image" src="https://github.com/user-attachments/assets/0f5e598f-8151-4b3c-90de-f07abeadaeb6" />

# using the case command
cat >casecheck.sh 
```bash
case $USER in
Ram | Robert)
echo "Welcome, $USER"
echo "Please enjoy your visit";;
Rahim)
echo "Special testing account";;
gganesh)
echo "$USER, Do not forget to log off when you're done";;
*)
echo "Sorry, you are not allowed here";;
esac
```
$ chmod 755 casecheck.sh 
 
$ ./casecheck.sh 
## output:

<img width="457" height="45" alt="image" src="https://github.com/user-attachments/assets/4298bd19-dbac-42ab-bbdc-50732959c4e3" />

cat > whiletest
```bash
#!/bin/bash
#while command test
var1=10
while [ $var1 -gt 0 ]
do
echo $var1
var1=$[ $var1 - 1 ]
done
```
$ chmod 755 whiletest.sh
 
$ ./whiletest.sh
## output:

<img width="458" height="244" alt="image" src="https://github.com/user-attachments/assets/c7d50257-b407-4c54-879a-e81860926d7a" />
 
cat untiltest.sh 
```bash
\#using the until command
var1=100
until [ $var1 -eq 0 ]
do
echo $var1
var1=$[ $var1 - 25 ]
done
``` 
$ chmod 755 untiltest.sh
$ ./untiltest.sh

 ## output:
 <img width="554" height="141" alt="image" src="https://github.com/user-attachments/assets/791a0897-e7f1-4114-8984-9a4897a9afa9" />

 
cat forin1.sh 
```bash
\#!/bin/bash
\#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
 ```
 
$ chmod 755 forin1.sh
$ ./forin1.sh

 ## output:
 <img width="629" height="198" alt="image" src="https://github.com/user-attachments/assets/846aca77-c981-4b87-9918-428f202db6b1" />

 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
 ```
 
$ chmod 755 forin2.sh
$ ./forin2.sh

 ## output:
 <img width="633" height="134" alt="image" src="https://github.com/user-attachments/assets/409e7fe8-94ae-4ee2-8e0f-eae54ed0c8f0" />

cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
```
$ chmod 755 forin2.sh
 
$ ./forin2.sh 
## output:
<img width="633" height="134" alt="image" src="https://github.com/user-attachments/assets/3226afca-47d8-4f6e-9101-f083d7470cf3" />

cat forin3.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```
$ chmod > 755 forin3.sh
$ ./forin3.sh 
 ## output:
 <img width="639" height="204" alt="image" src="https://github.com/user-attachments/assets/86896796-56a8-4c68-bf96-3a59fe0b4de0" />

cat forin1.sh 
```bash
#!/bin/bash
# basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
```
$ chmod 755 forin1.sh
$ ./forin1.sh

## OUTPUT
<img width="637" height="161" alt="image" src="https://github.com/user-attachments/assets/59324ddb-bafb-424f-bea8-f9c6238cbf29" />

cat > forinfile.sh 
```bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file“
done
```
$ chmod 777 forinfile.sh
$ cat > cities
Hyderabad
Alampur
Basara
Warangal
Adilabad
Bhadrachalam
Khammam

$ chmod 777 cities

$ ./cities

## OUTPUT

<img width="636" height="178" alt="image" src="https://github.com/user-attachments/assets/35ff652b-a692-4657-9d76-234d7d5d06b7" />


cat > forctype.sh 
```bash
#!/bin/bash
# testing the C-style for loop
for (( i=1; i <= 5; i++ ))
do
echo "The value of i is $i"
done
````
$ chmod 755 forctype.sh
$ ./forctype.sh 
## OUTPUT
<img width="626" height="138" alt="image" src="https://github.com/user-attachments/assets/7f7c2fc1-fb12-417c-bccc-7cb83a46dad2" />

cat > forctype1.sh 
```bash
#!/bin/bash
# multiple variables
for (( a=1, b=5; a <= 5; a++, b-- ))
do
echo "$a - $b"
done
```
$ chmod 755 forctype.sh
$ ./forctype.sh 
## OUTPUT
<img width="626" height="138" alt="image" src="https://github.com/user-attachments/assets/1076a656-e81c-4ce0-8ecf-06f0eabf0270" />


cat > fornested1.sh 
```bash
#!/bin/bash
# nesting for loops
for (( a = 1; a <= 3; a++ ))
do
echo "Starting loop $a:"
for (( b = 1; b <= 3; b++ ))
do
echo " Inside loop: $b"
done
done
```
$ chmod 755 fornested1.sh
 
$ ./fornested1.sh 
 ## OUTPUT

<img width="629" height="288" alt="image" src="https://github.com/user-attachments/assets/0fb8dc58-0fff-450d-aac2-8c5e424d87c5" />

 
cat > forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
break
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```


$ chmod 755 forbreak.sh
 
$ ./forbreak.sh 
## OUTPUT
 <img width="656" height="78" alt="image" src="https://github.com/user-attachments/assets/bab79c6c-e275-47ba-b486-1e8bc0773a2b" />
 
cat > forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
continue
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```

 
$ chmod 755 forcontinue.sh
 
$ ./forcontinue.sh 
## OUTPUT
 <img width="656" height="115" alt="image" src="https://github.com/user-attachments/assets/8bba22c4-64e9-459d-a759-4636cd9915e2" />


cat > exread.sh 
```bash
#!/bin/bash
# testing the read command
echo -n "Enter your name: "
read name
echo "Hello $name, welcome to my program. "
 ```
 
$ chmod 755 exread.sh 
 
$ ./exread.sh 
## OUTPUT


 cat exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
$ chmod 755 exread1.sh 
$ ./exread1.sh 

## OUTPUT
<img width="653" height="70" alt="image" src="https://github.com/user-attachments/assets/904a6359-f69a-4030-a0af-4a9404b1eae4" />


 
cat > funcex.sh
```bash
#!/bin/bash
# trying to access script parameters inside a function
function func {
echo $[ $1 * $2 ]
}
if [ $# -eq 2 ]
then
value=`func $1 $2`
echo "The result is $value"
else
echo "Usage: badtest1 a b"
fi
```
## OUTPUT
 ./funcex.sh 
<img width="653" height="49" alt="image" src="https://github.com/user-attachments/assets/94684c33-174e-436f-9e15-de977e3002b5" />


 
 ./funcex.sh 1 2
<img width="653" height="49" alt="image" src="https://github.com/user-attachments/assets/0543d9f8-24e6-4851-a0c9-1c5152b400fa" />


 
cat > argshift.sh
```bash
#!/bin/bash 
 while (( "$#" )); do 
  echo $1 
  shift 
done
```
$ chmod 777 argshift.sh

## OUTPUT
$ ./argshift.sh 1 2 3
 
 cat argshift1.sh
```bash
 #/bin/bash 
 # store arguments in a special array 
args=("$@") 
# get number of elements 
ELEMENTS=${#args[@]} 
 # echo each element in array  
# for loop 
for (( i=0;i<$ELEMENTS;i++)); do 
    echo ${args[${i}]} 
done
```
$ chmod 777 argshift.sh
## OUTPUT
$ ./argshift.sh 1 2 3
 
cat argshift.sh
```bash
#!/bin/bash 
set -x 
while (( "$#" )); do 
  echo $1 
  shift 
done
set +x
```
## OUTPUT
 ./argshift.sh 1 2 3
 
 
cat > nc.awk
```bash
BEGIN{}
{
print len=length($0),"\t",$0 
wordcount+=NF
chrcnt+=len
}
END {
print "total characters",chrcnt 
print "Number of Lines are",NR
print "No of Words count:",wordcount
}
 ```
cat>data.dat
```bash
bcdfghj
abcdfghj
bcdfghj
ebcdfghj
bcdfghj
ibcdfghj
bcdfghj
obcdfghj
bcdfghj
ubcdfghj
```
awk -f nc.awk data.dat
## OUTPUT 
 
cat > palindrome.sh
```bash
#num=545
echo "Enter the number"
read num
s=0
rev=""
temp=$num
while [ $num -gt 0 ]
do
	# Get Remainder
	s=$(( $num % 10 ))
	# Get next digit
	num=$(( $num / 10 ))
	# Store previous number and
	# current digit in reverse
	rev=$( echo ${rev}${s} )
done
if [ $temp -eq $rev ];
then
	echo "Number is palindrome"
else
	echo "Number is NOT palindrome"
fi
```
## OUTPUT 


# RESULT:
The Commands are executed successfully.
