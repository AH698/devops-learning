# Bash Notes

A summary of the Bash scripting concepts I have covered while building my DevOps foundations.

## BASH BASICS

Bash allows Linux commands to be combined into scripts to automate tasks.

A Bash script commonly starts with:

```bash
#!/bin/bash
```

## VARIABLES AND USER INPUT

Variables store information that can be reused throughout a script.

```bash
name="Aryaan"
echo "$name"
```

I used `read -r` to collect user input and store it in variables.

```bash
read -r filename
```

## CONDITIONS

Conditional statements allow a script to make decisions.

```bash
if condition; then
    command
else
    command
fi
```

I also used file checks such as:

- `-f` - Checks for a regular file
- `-d` - Checks for a directory
- `-e` - Checks whether something exists

This was useful for validating files before creating, renaming or deleting them.

## LOOPS

I worked with three main types of loops:

- `for` - Repeats through a set of items
- `while` - Runs while a condition is true
- `until` - Runs until a condition becomes true

Loops allowed me to repeat tasks without writing the same commands multiple times.

## CASE STATEMENTS

I used `case` statements when creating scripts with multiple user options.

```bash
case "$choice" in
    1)
        echo "Option 1"
        ;;
    *)
        echo "Invalid option"
        ;;
esac
```

This was particularly useful when building interactive menus.

## FUNCTIONS AND EXIT CODES

Functions allowed me to organise reusable sections of code.

I also learned how exit codes communicate whether a script completed successfully.

`exit 0` normally represents success.

`exit 1` normally represents an error.

## IFS AND TEXT PROCESSING

I used `IFS` with `read -r` when processing configuration-style data.

```bash
while IFS= read -r line; do
    echo "$line"
done < file.txt
```

This gave me more control over how input was read and processed.

## PRACTICAL SCRIPTS

During the Bash Arena exercises, I combined these concepts to build more complete scripts.

These included:

- An interactive file management menu
- A configuration file parser
- A disk report
- Backup creation using `tar`
- Backup rotation that kept the five most recent backups
- Scripts combining conditions, loops, variables and file checks

For backup rotation, I used commands including `ls -t` and `tail -n +6` to identify older backups.

## KEY TAKEAWAYS

Bash has helped me move from running Linux commands individually to combining them into useful automation.

The main concepts I have developed are variables, user input, conditions, loops, case statements, functions, file checks and exit codes.

The biggest lesson has been understanding the logic of a task first. Once I know what needs to happen and what conditions need to be checked, writing the script becomes much easier.
