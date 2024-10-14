## :octocat: Working with Git and Bash
> ### Creating, moving, deleting, and updating files and directories
<details> 
<summary>Open Task 1</summary>

#### Commands & Description
  
```bash
cd                                       # Home directory
pwd                                      # Current directory path
mkdir test1                              # Create a test1 directory
cd /c/Users/darya/test1/                 # Go to the test1 directory
touch 1.txt 2.txt 3.txt                  # Create file 1, 2, 3 inside the test1 directory
ls                                       # Contents of the test1 directory
cd                                       # Home directory
mkdir test2                              # Create a test2 directory inside the home directory
rmdir test2                              # Delete the test2 directory

cd /c/Users/darya/test1/                 # Delete file 2 from the test1 directory
rm 2.txt

cd                                       # Create a test3 directory in the home directory and add two files to it
mkdir test3
cd /c/Users/darya/test3/
touch 4.txt 5.txt

cd                                       # Delete the test3 directory
rm -r test3

mkdir test4                              # Create a test4 directory in the home directory

cd /c/Users/darya/test1/                 # Move files 1 and 3 from the test1 directory to the test4 directory
mv 1.txt 3.txt /c/Users/darya/test4/

cd /c/Users/darya/test4/                 # Add three lines to file 1 with the word "line"
echo -e "line\nline\nline\n" > 1.txt

cat 1.txt                                # File 1 content
echo -e "line\nline\nline\n" > 3.txt     # Add three lines to file 3 with the word "line"
cat 1.txt 3.txt                          # Contents of two files 1 and 3
sed -i 's/line/new_line/g' 1.txt         # Replace all the lines in file 1
```
</details>

> ### Finding, adding and replacing info, pinging, sending requests

<details>
<summary>Open Task 2</summary>

#### Commands & Description

```bash
cd                                                                                    # Home directory
mkdir test3                                                                           # Create a test3 directory

cd /c/Users/darya/test3/                                                              # Add three files 4, 5, and 6 to the test3 directory, each with 4 rows row1, row2, row3, row4
touch 4.txt 5.txt 6.txt
echo -e "row1\nrow2\nrow3\nrow4\n" | tee -a 4.txt 5.txt 6.txt

grep "row2" 5.txt                                                                     # Find the line "row2" in file 5
cd + grep -r "row*" test3/                                                            # Find the line "row" in the test3 directory

cd /c/Users/darya/test3/                                                              # Number of lines with "row" content in the file 6
grep -c "row*" 6.txt

cd                                                                                    # Find file 5 in the test3 directory
find /c/Users/darya/test3 -name "5.txt"

cd /c/Users/darya/test3/                                                              # Using find command, delete file 5
find . -type f -name "5.txt" -exec rm -f {} \;

echo "test" >> 4.txt                                                                  # Using echo command, add the word "test" to file 4
sed -i 's/test/fail/g' 4.txt                                                          # Replace the word "test" in file 4 with "fail"
echo "test" >> 4.txt                                                                  # Add the word "test" to file 4 so that the contents are preserved
ps aux                                                                                # View all processes on the system
kill 666                                                                              # Kill the 666 process in the console
ping rusau.net                                                                        # Check the availability of rusau.net using ping
ping -c 5 rusau.net                                                                   # Send 5 packages to rusau.net
curl https://petstore.swagger.io/v2/pet/findByStatus?status=available                 # Using GET and curl command, get information about registered pets with any status at https://petstore.swagger.io/
curl -X POST https://reqres.in/api/users --data "name=morpheus" --data "job=leader"   # Using POST and curl command, create a new user at https://reqres.in/

curl -X 'POST' \                                                                      # Using POST and the curl command, create a new user at https://petstore.swagger.io/
  'https://petstore.swagger.io/v2/user' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "id": 0,
  "username": "string",
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "password": "string",
  "phone": "string",
  "userStatus": 0
}'
```
</details>
