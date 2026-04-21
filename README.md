# -File-Handling-Programs
# Aim:
To demonstrate the use of file pointer manipulation functions, specifically f.tell() and f.seek(), to navigate and read specific portions of a text file in Python.

# Procedure:
1.Open: Open a file named merge.txt in read mode ("r").

2.Track: Use f.tell() to see where the cursor starts (usually at 0).

3.Move (First Jump): Use f.seek(4) to jump the cursor to the 4th character.

4.Read: Read and print the next 5 characters using f.read(5).

5.Move (Second Jump): Use f.seek(10) to move the cursor to the 10th character from the start.

6.Verify: Check the new position using f.tell().

7.Read Again: Read and print the next 10 characters from that point.

8.Close: Close the file to save memory.

# code:
```
def file_cursor_exercise():
    # Note: Ensure "merge.txt" exists in your directory before running
    try:
        f = open("merge.txt", "r")
        
        # 1. Print the initial position
        print(f"Initial position: {f.tell()}")
        
        # 2. Move the cursor to 4th position
        f.seek(4, 0)
        
        # 3. Display next 5 characters
        print(f"Next 5 characters: {f.read(5)}")
        
        # 4. Move the cursor to the next 10 characters (absolute position 10)
        # Note: In text mode, seek is usually relative to the start (0)
        f.seek(10, 0)
        
        # 5. Print the current cursor position
        print(f"Current cursor position: {f.tell()}")
        
        # 6. Print next 10 characters from the current cursor position
        print(f"Next 10 characters: {f.read(10)}")
        
        f.close()
    except FileNotFoundError:
        print("Error: 'merge.txt' not found. Please create the file first.")

file_cursor_exercise()

```

# output:
```
Initial position: 0
Next 5 characters: EFGHJ
Current cursor position: 10
Next 10 characters: KLMNOPQRST
```

# Result:
The program successfully demonstrates how to use f.seek() to jump to specific byte offsets and f.tell() to track the cursor's current position within a text file.
