### Lecture Link
- https://youtu.be/mfsqaNtQdQc?si=-HLPvkwRi0cA1S3C
---
### Redirection
#### Descriptors
- 0 -- INPUT       [default = keyboard]
- 1 -- OUTPUT   [default = Screen]
- 2 -- ERROR      [default = Screen]
---
#### Redirect
- If you want to show the output or the error into another file instead of showing it immediate.
```bash
# Get the output into result.txt
# 1 is optioanl
ls -al file.txt 1> result.txt # == ls -al file.txt > result.txt
# Get the error into error.txt
ls -al file.txt 2> error.txt
# If there is errors put in error.txt and if there is output put in result.txt
ls -al file.txt > result.txt 2> error.txt
```
- If your commands run successfuly but doesn't have output result file in our example will be created and will be empty.

```bash 
# To avoid override file use >>
ls -al file.txt >> result.txt 2>> error.txt
```

---
### Difference [ > and >>]
- > used to override content of file [delete the old and write all I will give]
- >> used to add to file [write new data without delete old data]
---
### Cat `<<EOF>>`

```bash
# What this << mean?
# We said before that < == input  and << mean write withot override.
# This mean take that input till you find this word EOF then >> redirect the output into this file.
# You can change EOF to any other word
cat <<EOF>> file.txt
Hello 
I write you from Linux Admin Course
EOF
```

```bash
# This script override file called lec.txt then write those commands till found EOF word
cat <<EOF>lec.txt  # different cause <<EOF> 
ls
cal
date
EOF
```

```bash 
# Another way to write script 
# Same effect of above
cat > lec.txt <<ANWAR  
ls
cal
date
ANWAR
```

---
### File Type 
- In Linux File extention doesn't effect cause system see the content of file not extention.
- In windows if you named `file.txt` to `file.mp3` it will be converted in Linux it will still ASCII text.
```bash
# To know the file type
file <path/to/file>
```
---
### Pipe |
#### More
+ Let you navigate by arrows till you reach end then exit.
#### Less 
-  Let you navigate by arrows till you reach end but not exit to exit press [q].
#### |
- Pipe make the output of command on the left be the input in the right.
```bash
# Let -R recursive mean show sub files and directores 
# After listing all sub files and directories of / use command less
ls -lR / | less
```
