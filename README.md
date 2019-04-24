# names
a dictionary cominator to find fancy names

## usage
To combine words from list a to list b in different directions you need two files. In the lists folder there are two examples.

This is the minimum argument requirements

```
$ ./pynames -a lists/start.txt -b lists/end.txt
-----------------------------------------
A1
A2
A42
B1
B2
B42
C1
C2
C42
AA
AB
AC
BA
BB
BC
CA
CB
CC
11
12
142
21
22
242
421
422
4242
1A
1B
1C
2A
2B
2C
42A
42B
42C
-----------------------------------------
Max Length: 255
Append Words: True
Lists: ab,ba,aa,bb
Combinations: 36
```

It generates 36 word combinations out of A+B, B+A, A+A and B+B. 

## filter output
There are some options to filter or reduce the output:

### list only combinations from list A+B and B+A
```
$ ./pynames -a lists/start.txt -b lists/end.txt -l "ab,ba"
-----------------------------------------
A1
A2
A42
B1
B2
B42
C1
C2
C42
1A
1B
1C
2A
2B
2C
42A
42B
42C
-----------------------------------------
Max Length: 255
Append Words: True
Lists: ['ab', 'ba']
Combinations: 18
```

### list only combinations with max length of 2
```
$ ./pynames -a lists/start.txt -b lists/end.txt -m 2
-----------------------------------------
A1
A2
B1
B2
C1
C2
AA
AB
AC
BA
BB
BC
CA
CB
CC
11
12
21
22
1A
1B
1C
2A
2B
2C
-----------------------------------------
Max Length: 2
Append Words: True
Lists: ab,ba,aa,bb
Combinations: 25
```

### list only combinatins which starts with string
```
$ ./pynames -a lists/start.txt -b lists/end.txt -s A
-----------------------------------------
A1
A2
A42
AA
AB
AC
-----------------------------------------
Filter A: A
Max Length: 255
Append Words: True
Lists: ab,ba,aa,bb
Combinations: 6
```

### list only combinations which ends with string
```
$ ./pynames -a lists/start.txt -b lists/end.txt -e B
-----------------------------------------
AB
BB
CB
1B
2B
42B
-----------------------------------------
Filter B: B
Max Length: 255
Append Words: True
Lists: ab,ba,aa,bb
Combinations: 6
```

### list only combinations which contains string
```
$ ./pynames -a lists/start.txt -b lists/end.txt -c AB
-----------------------------------------
AB
-----------------------------------------
Contains: AB
Max Length: 255
Append Words: True
Lists: ab,ba,aa,bb
Combinations: 1
```

### list combinations with space between
```
$ ./pynames -a lists/start.txt -b lists/end.txt --noappend -m 2
-----------------------------------------
A 1
A 2
B 1
B 2
C 1
C 2
A A
A B
A C
B A
B B
B C
C A
C B
C C
1 1
1 2
2 1
2 2
1 A
1 B
1 C
2 A
2 B
2 C
-----------------------------------------
Max Length: 2
Append Words: False
Lists: ab,ba,aa,bb
Combinations: 25
```

### list max 10 results
```
$ ./pynames -a lists/start.txt -b lists/end.txt -n 10
-----------------------------------------
A1
A2
A42
B1
B2
B42
C1
C2
C42
AA
-----------------------------------------
Max Length: 255
Max Count: 10
Append Words: True
Lists: ab,ba,aa,bb
Combinations: 10
```

## requirements
This is a python script, so you need at least python version 2 running.


