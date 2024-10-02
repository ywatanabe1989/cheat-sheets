# Shell Script Cheat Sheet

## 1. Script Structure and Execution
### Basic Structure
```bash
#!/bin/bash
# Your code here
```

### Scripting with Path
```bash
#!/bin/bash
script_dir="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd)"
source "$script_dir/another_script.sh"
```
or
```bash
$ sh /path/to/your_script.sh
```

## 2. Variables and Data Structures
### Variables
```bash
variable_name="value"
echo $variable_name
```

### Lists
```bash
my_list=("item1" "item2" "item3")
echo ${my_list[0]}  # Access first item
echo ${#my_list[@]}  # Get list length
for item in "${my_list[@]}"; do
    echo $item
done
```

## 3. Control Structures
### Conditionals
```bash
if [ condition ]; then
    # code
elif [ condition ]; then
    # code
else
    # code
fi
```

### Loops
#### For loop
```bash
for i in {1..5}
do
    echo $i
done
```

#### While loop
```bash
while [ condition ]
do
    # code
done
```

## 4. Functions
```bash
function_name() {
    # code
}

function_name
```

## 5. File and Directory Operations
### Checkers
```bash
[ -f file ]  # File exists and is a regular file
[ -d dir ]   # Directory exists
[ -L link ]  # Symbolic link exists
[ -r file ]  # File is readable
[ -w file ]  # File is writable
[ -x file ]  # File is executable
[ file1 -nt file2 ]  # file1 is newer than file2
[ file1 -ot file2 ]  # file1 is older than file2
```

### File Operations
```bash
if [ -f "file.txt" ]; then
    echo "File exists"
fi

if [ -d "directory" ]; then
    echo "Directory exists"
fi
```

## 6. String and Numeric Operations
### String Operations
```bash
[ "$string1" = "$string2" ]  # True if strings are equal
[ "$string1" != "$string2" ]  # True if strings are not equal
[ -z "$string" ]  # True if string is empty
[ -n "$string" ]  # True if string is not empty
```

### String Manipulation
```bash
${string#pattern}  # Remove shortest match of pattern from start
${string##pattern}  # Remove longest match of pattern from start
${string%pattern}  # Remove shortest match of pattern from end
${string%%pattern}  # Remove longest match of pattern from end
${string/pattern/replacement}  # Replace first match of pattern
${string//pattern/replacement}  # Replace all matches of pattern
${#string}  # String length
```

### Numeric Comparisons
```bash
[ $a -lt $b ]  # True if a is less than b
[ $a -le $b ]  # True if a is less than or equal to b
[ $a -gt $b ]  # True if a is greater than b
[ $a -ge $b ]  # True if a is greater than or equal to b
[ $a -eq $b ]  # True if a is equal to b
[ $a -ne $b ]  # True if a is not equal to b
```

## 7. Command Operations
### Command Substitution
```bash
result=$(command)
echo "The result is $result"
```

### Aliasing
```bash
alias ll='ls -la'
unalias ll  # Remove alias
```

## 8. Input and Arguments
### Arguments
```bash
$1, $2, $3  # First, second, third argument
$#  # Number of arguments
$@  # All arguments
shift # Shift positional parameters to the left
```

### Reading User Input
```bash
read -p "Enter your name: " name
echo "Hello, $name"
```

## 9. Error Handling and Debugging
### Error Handling
```bash
set -e  # Exit immediately if a command exits with a non-zero status
trap 'echo "Error on line $LINENO"' ERR
```

### Debugging
```bash
set -x  # Enable debugging
set +x  # Disable debugging
```

## 10. Arithmetic Operations
```bash
result=$((5 + 3))
echo $result

# Increment/decrement
((var++))
((var--))

# Compound assignment
((var += 5))
((var *= 2))
```

## 11. Process Management
### Background Processes
```bash
command &
wait  # Wait for all background processes to finish
```

### Process Substitution
```bash
diff <(command1) <(command2)
```

### Subshells
```bash
(cd /tmp && command)  # Run command in a subshell
```

## 12. File Descriptors and Redirection
```bash
command > file  # Redirect stdout to file
command 2> file  # Redirect stderr to file
command &> file  # Redirect both stdout and stderr to file
command < file  # Redirect file to stdin
command << EOF  # Here document
content
EOF
command | tee file  # Write output to both file and stdout
command |& tee file  # Write both stdout and stderr to file and stdout
command > /dev/null  # Discard stdout
command 2> /dev/null  # Discard stderr
command &> /dev/null  # Discard both stdout and stderr
```

## 13. Useful Built-in Variables
```bash
$?  # Exit status of last command
$$  # PID of current shell
$!  # PID of last background process
$0  # Name of the script
$RANDOM  # Random number between 0 and 32767
<!-- 1. 
 !-- 1. Script Structure and Execution
 !--    - Basic Structure
 !--    - Scripting with Path
 !-- 
 !-- 2. Variables and Data Structures
 !--    - Variables
 !--    - Lists
 !-- 
 !-- 3. Control Structures
 !--    - Conditionals
 !--    - Loops (For and While)
 !-- 
 !-- 4. Functions
 !-- 
 !-- 5. File and Directory Operations
 !--    - Checkers
 !--    - File Operations
 !-- 
 !-- 6. String and Numeric Operations
 !--    - String Operations
 !--    - String Manipulation
 !--    - Numeric Comparisons
 !-- 
 !-- 7. Command Operations
 !--    - Command Substitution
 !--    - Aliasing
 !-- 
 !-- 8. Input and Arguments
 !--    - Arguments
 !--    - Reading User Input
 !-- 
 !-- 9. Error Handling and Debugging
 !--    - Error Handling
 !--    - Debugging
 !-- 
 !-- 10. Arithmetic Operations
 !-- 
 !-- 11. Process Management
 !--     - Background Processes
 !--     - Process Substitution
 !--     - Subshells
 !-- 
 !-- 12. File Descriptors and Redirection
 !-- 
 !-- 13. Useful Built-in Variables
 !-- 
 !-- 
 !-- ## Basic Structure
 !-- ```bash
 !-- #!/bin/bash
 !-- # Your code here
 !-- ```
 !-- 
 !-- ## Scripting with Path
 !-- ```bash
 !-- #!/bin/bash
 !-- script_dir="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd)"
 !-- source "$script_dir/another_script.sh"
 !-- ```
 !-- or
 !-- ``` bash
 !-- $ sh /path/to/your_script.sh
 !-- ```
 !-- 
 !-- ## Variables
 !-- ```bash
 !-- variable_name="value"
 !-- echo $variable_name
 !-- ```
 !-- 
 !-- ## Conditionals
 !-- ```bash
 !-- if [ condition ]; then
 !--     # code
 !-- elif [ condition ]; then
 !--     # code
 !-- else
 !--     # code
 !-- fi
 !-- ```
 !-- 
 !-- ## Loops
 !-- ### For loop
 !-- ```bash
 !-- for i in {1..5}
 !-- do
 !--     echo $i
 !-- done
 !-- ```
 !-- 
 !-- ### While loop
 !-- ```bash
 !-- while [ condition ]
 !-- do
 !--     # code
 !-- done
 !-- ```
 !-- 
 !-- ## Functions
 !-- ```bash
 !-- function_name() {
 !--     # code
 !-- }
 !-- 
 !-- function_name
 !-- ```
 !-- 
 !-- ## Checkers
 !-- ```bash
 !-- | Check | Description |
 !-- |-------|-------------|
 !-- | `-f file` | File exists and is a regular file |
 !-- | `-d dir` | Directory exists |
 !-- | `-L link` | Symbolic link exists |
 !-- | `-e file_or_dir` | File or directory exists |
 !-- | `-r file` | File is readable |
 !-- | `-w file` | File is writable |
 !-- | `-x file` | File is executable |
 !-- | `file1 -nt file2` | file1 is newer than file2 |
 !-- | `file1 -ot file2` | file1 is older than file2 |
 !-- | `command -v program >/dev/null 2>&1` | Program is available in PATH |
 !-- | `type -P program >/dev/null 2>&1` | Program is available as an external command |
 !-- ```
 !-- 
 !-- ## String Operations
 !-- ```bash
 !-- # String comparison
 !-- [ "$string1" = "$string2" ]  # True if strings are equal
 !-- [ "$string1" != "$string2" ]  # True if strings are not equal
 !-- [ -z "$string" ]  # True if string is empty
 !-- [ -n "$string" ]  # True if string is not empty
 !-- ```
 !-- 
 !-- ## Numeric Comparisons
 !-- ```bash
 !-- [ $a -lt $b ]  # True if a is less than b
 !-- [ $a -le $b ]  # True if a is less than or equal to b
 !-- [ $a -gt $b ]  # True if a is greater than b
 !-- [ $a -ge $b ]  # True if a is greater than or equal to b
 !-- [ $a -eq $b ]  # True if a is equal to b
 !-- [ $a -ne $b ]  # True if a is not equal to b
 !-- ```
 !-- 
 !-- ## Command Substitution
 !-- ```bash
 !-- result=$(command)
 !-- echo "The result is $result"
 !-- ```
 !-- 
 !-- ## Error Handling
 !-- ```bash
 !-- set -e  # Exit immediately if a command exits with a non-zero status
 !-- trap 'echo "Error on line $LINENO"' ERR
 !-- ```
 !-- 
 !-- ## Arguments
 !-- ```bash
 !-- $1, $2, $3  # First, second, third argument
 !-- $#  # Number of arguments
 !-- $@  # All arguments
 !-- shift # Shift positional parameters to the left
 !-- 
 !-- # Example
 !-- function handle_args() {
 !--     echo "First argument: $1"
 !--     echo "Second argument: $2"
 !--     echo "Third argument: $3"
 !--     echo "Number of arguments: $#"
 !--     echo "All arguments: $@"
 !--     
 !--     shift
 !--     echo "After shift, first argument: $1"
 !-- }
 !-- 
 !-- # Usage example
 !-- handle_args arg1 arg2 arg3 arg4
 !-- ```
 !-- 
 !-- ## Reading User Input
 !-- ```bash
 !-- read -p "Enter your name: " name
 !-- echo "Hello, $name"
 !-- ```
 !-- 
 !-- ## Lists
 !-- ```bash
 !-- my_list=("item1" "item2" "item3")
 !-- echo ${my_list[0]}  # Access first item
 !-- echo ${#my_list[@]}  # Get list length
 !-- for item in "${my_list[@]}"; do
 !--     echo $item
 !-- done
 !-- 
 !-- ## Aliasing
 !-- ```bash
 !-- alias ll='ls -la'
 !-- unalias ll  # Remove alias
 !-- ```
 !-- 
 !-- 
 !-- ## Basic Structure and Setup
 !-- ```bash
 !-- #!/bin/bash
 !-- # Your code here
 !-- 
 !-- # Scripting with Path
 !-- script_dir="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd)"
 !-- source "$script_dir/another_script.sh"
 !-- ```
 !-- 
 !-- ## Variables and Data Structures
 !-- ```bash
 !-- # Variables
 !-- variable_name="value"
 !-- echo $variable_name
 !-- 
 !-- # Lists
 !-- my_list=("item1" "item2" "item3")
 !-- echo ${my_list[0]}  # Access first item
 !-- echo ${#my_list[@]}  # Get list length
 !-- for item in "${my_list[@]}"; do
 !--     echo $item
 !-- done
 !-- ```
 !-- 
 !-- ## Control Structures
 !-- ```bash
 !-- # Conditionals
 !-- if [ condition ]; then
 !--     # code
 !-- elif [ condition ]; then
 !--     # code
 !-- else
 !--     # code
 !-- fi
 !-- 
 !-- # For loop
 !-- for i in {1..5}
 !-- do
 !--     echo $i
 !-- done
 !-- 
 !-- # While loop
 !-- while [ condition ]
 !-- do
 !--     # code
 !-- done
 !-- ```
 !-- 
 !-- ## Functions
 !-- ```bash
 !-- function_name() {
 !--     # code
 !-- }
 !-- 
 !-- function_name
 !-- ```
 !-- 
 !-- ## File and Directory Operations
 !-- ```bash
 !-- # File Operations
 !-- if [ -f "file.txt" ]; then
 !--     echo "File exists"
 !-- fi
 !-- 
 !-- if [ -d "directory" ]; then
 !--     echo "Directory exists"
 !-- fi
 !-- 
 !-- # File and Directory Checks
 !-- [ -f file ]  # True if file exists and is a regular file
 !-- [ -d dir ]   # True if dir exists and is a directory
 !-- [ -L link ]  # True if link exists and is a symbolic link
 !-- [ -r file ]  # True if file is readable
 !-- [ -w file ]  # True if file is writable
 !-- [ -x file ]  # True if file is executable
 !-- [ file1 -nt file2 ]  # True if file1 is newer than file2
 !-- [ file1 -ot file2 ]  # True if file1 is older than file2
 !-- ```
 !-- 
 !-- ## Command Operations
 !-- ```bash
 !-- # Command Substitution
 !-- result=$(command)
 !-- echo "The result is $result"
 !-- 
 !-- # Error Handling
 !-- set -e  # Exit immediately if a command exits with a non-zero status
 !-- trap 'echo "Error on line $LINENO"' ERR
 !-- 
 !-- # Aliasing
 !-- alias ll='ls -la'
 !-- unalias ll  # Remove alias
 !-- ```
 !-- 
 !-- ## Input and Arguments
 !-- ```bash
 !-- # Arguments
 !-- $1, $2, $3  # First, second, third argument
 !-- $#  # Number of arguments
 !-- $@  # All arguments
 !-- shift # Shift positional parameters to the left
 !-- 
 !-- # Reading User Input
 !-- read -p "Enter your name: " name
 !-- echo "Hello, $name"
 !-- ```
 !-- 
 !-- ## Comparisons
 !-- ```bash
 !-- # Numeric Comparisons
 !-- [ $a -lt $b ]  # True if a is less than b
 !-- [ $a -le $b ]  # True if a is less than or equal to b
 !-- [ $a -gt $b ]  # True if a is greater than b
 !-- [ $a -ge $b ]  # True if a is greater than or equal to b
 !-- [ $a -eq $b ]  # True if a is equal to b
 !-- [ $a -ne $b ]  # True if a is not equal to b
 !-- ```
 !-- 
 !-- 
 !-- # String manipulation
 !-- ``` bash
 !-- ${string#pattern}  # Remove shortest match of pattern from start
 !-- ${string##pattern}  # Remove longest match of pattern from start
 !-- ${string%pattern}  # Remove shortest match of pattern from end
 !-- ${string%%pattern}  # Remove longest match of pattern from end
 !-- ${string/pattern/replacement}  # Replace first match of pattern
 !-- ${string//pattern/replacement}  # Replace all matches of pattern
 !-- ${#string}  # String length
 !-- ```
 !-- 
 !-- ## Arithmetic Operations
 !-- ```bash
 !-- result=$((5 + 3))
 !-- echo $result
 !-- 
 !-- # Increment/decrement
 !-- ((var++))
 !-- ((var--))
 !-- 
 !-- # Compound assignment
 !-- ((var += 5))
 !-- ((var *= 2))
 !-- ```
 !-- 
 !-- ## Process Management
 !-- ```bash
 !-- # Background processes
 !-- command &
 !-- wait  # Wait for all background processes to finish
 !-- 
 !-- # Process substitution
 !-- diff <(command1) <(command2)
 !-- 
 !-- # Subshells
 !-- (cd /tmp && command)  # Run command in a subshell
 !-- ```
 !-- 
 !-- ## File Descriptors and Redirection
 !-- ```bash
 !-- command > file  # Redirect stdout to file
 !-- command 2> file  # Redirect stderr to file
 !-- command &> file  # Redirect both stdout and stderr to file
 !-- command < file  # Redirect file to stdin
 !-- command << EOF  # Here document
 !-- content
 !-- EOF
 !-- command | tee file  # Write output to both file and stdout
 !-- command |& tee file  # Write both stdout and stderr to file and stdout
 !-- command > /dev/null  # Discard stdout
 !-- command 2> /dev/null  # Discard stderr
 !-- command &> /dev/null  # Discard both stdout and stderr
 !-- ```
 !-- 
 !-- ## Debugging
 !-- ```bash
 !-- set -x  # Enable debugging
 !-- set +x  # Disable debugging
 !-- ```
 !-- 
 !-- ## Useful Built-in Variables
 !-- ```bash
 !-- $?  # Exit status of last command
 !-- $$  # PID of current shell
 !-- $!  # PID of last background process
 !-- $0  # Name of the script
 !-- $RANDOM  # Random number between 0 and 32767
 !-- ``` -->
