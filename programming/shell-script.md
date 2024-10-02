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
### File Checkers
```bash
[ -f file ]  # File exists and is a regular file
[ -d dir ]   # Directory exists
[ -e file_or_dir ]  # File or directory exists
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
## Command Checkers
| Check | Description |
|-------|-------------|
| `command -v program >/dev/null 2>&1` | Program is available in PATH |
| `type -P program >/dev/null 2>&1` | Program is available as an external command |


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

# Example in function
function handle_args() {
    echo "First argument: $1"
    echo "Second argument: $2"
    echo "Third argument: $3"
    echo "Number of arguments: $#"
    echo "All arguments: $@"
    
    shift
    echo "After shift, first argument: $1"
}

# Usage example
handle_args arg1 arg2 arg3 arg4
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
```
