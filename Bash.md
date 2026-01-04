# BASH ADVANCE COMMANDS

## Basic Directory and File Commands

1. `pwd`  
   **Description:** Present Working Directory path.

2. `ls`  
   **Description:** View directories and files in a folder.  
   - `ls -R` - View subdirectories of directories.  
   - `ls -t` - View when the files were last modified.  
   - `ls -l` - View permissions, last modified date, size in bytes of a folder.  
   - `ls -lt` - View last modified files with time included.  
   - `ls -la` - View all items, including hidden items.  
   - `ls -lRa` - View hidden items in subdirectories recursively.  
   - `ls -lr` - Show all files in reverse order.  
   - `ls -s` - View directories by size.  
   - `ls *.FILE_EXTENSION_NAME` - View files of a specific type.  
   - `ls Zoo*` - View files with "Zoo" in their name.  
   - `ls ..` - List all directories and folders.

3. `cd`  
   **Description:** Change directory.  
   - `cd ..` - Go to the previous directory.  
   - `cd ../../` - Go back two levels.

4. `touch`  
   **Description:** Create a file. Example: `touch a.js`.

5. `cat`  
   **Description:**  
   - View file contents. Example: `cat a.js`.  
   - Write to a file: `cat > a.txt`. Use `Ctrl+D` to save and exit.  
   - Append to an existing file: `cat >> a.txt`.

## Directory Management Commands

6. `mkdir`  
   **Description:** Create a directory.  
   - Example: `mkdir test`.  
   - `mkdir test && cd test` - Create and enter the directory.  
   - `mkdir -p frontend/scripts` - Create nested directories.

7. `mv`  
   **Description:** Move or rename files.  
   - Example: `mv script.js runtime_script.js`.  
   - Rename: `mv filepath/newname`.

8. `cp`  
   **Description:** Copy files or directories.  
   - Example: `cp filepath new_filepath`.  
   - Copy directory: `cp -r`.

9. `rm`  
   **Description:** Delete files or directories.  
   - Example: `rm filename`.  
   - Delete folder: `rm -r folderpath`.

## File Permissions Commands

10. `chmod`  
    **Description:** Modify file permissions.  
    - `chmod ugo-rwx` - Add permissions for user (u), group (g), others (o) with read (r), write (w), execute (x).  
    - `chmod -R ugo-rwx` - Add permissions recursively for a folder.  
    - `chmod u+x filename` - Add execute permissions for the user.  
    - `chmod g+wx filename` - Add write and execute permissions for the group.  
    - `chmod 664 foldername` - Grant specific permissions (e.g., 6 = read + write).  
    - `chmod 777 foldername` - Grant all permissions.

## Viewing File Content

11. `echo 'Hello World'`  
    **Description:** Display a message.

12. `head filename`  
    **Description:** View the first 10 rows of a file.  
    - `head -20 filename` - View the first 20 rows.

13. `tail filename`  
    **Description:** View the last 10 rows of a file.  
    - `tail -n +25 filename | head -n +5` - View custom rows (e.g., rows 25–30).

14. `wc filename`  
    **Description:** View line count, word count, and character count.

## Searching with Grep

15. `grep "one" filename`  
    **Description:** Find occurrences of "one" in a file.  
    - `grep -c "one" filename` - Count occurrences.  
    - `grep -h "one" filename` - Case-sensitive search.  
    - `grep -hi "one" filename` - Case-insensitive search.  
    - `grep -hir "one" directoryname` - Search in a directory.  
    - `grep -w "one" filename` - Match entire words.  
    - `grep -o "one" filename` - Output matched parts only.

16. Contextual Search:  
    - `grep -A 5 ERROR filename` - Rows after "ERROR".  
    - `grep -B 5 ERROR filename` - Rows before "ERROR".  
    - `grep -C 5 ERROR filename` - Rows before and after "ERROR".

## File Manipulation with Sed

17. `sed`  
    **Description:** Stream editor for file manipulation.  
    - `sed -n '/ERROR/ p' filename` - Print lines containing "ERROR".  
    - `sed 's/ERROR/CRITICAL/' filename` - Replace "ERROR" with "CRITICAL".  
    - `sed -ibackup 's/ERROR/CRITICAL/' filename` - Create a backup while replacing.  
    - `sed '3 s/CRITICAL/VERYCRITICAL/' filename` - Replace in line 3.  
    - `sed '3,5 s/ERROR/CRITICAL/' filename` - Replace in lines 3–5.

## File Manipulation with AWK

18. `awk`  
    **Description:** Pattern scanning and processing.  
    - `awk '/ERROR/{print $0}' filename` - Print lines with "ERROR".  
    - `awk '{gsub(/ERROR/, "CRITICAL")}{print}' filename` - Replace "ERROR" with "CRITICAL".  
    - `awk '{print $1, $2}' filename` - Print specific columns.  
    - `awk -F "," '{print $1, $2}' filename` - Extract specific fields.  
    - `awk '{ if ($1 > 1598863888 ) {print $0} }' log.txt` - Filter rows based on condition.