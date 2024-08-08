---
title: Sudoku (C)
date: 2023-06-01
tags:
  - Sudoku
  - Heuristics
  - Grid generation
---

The goal of this project was to generate random Sudoku grids of sizes from 1x1 to 64x64 and to solve them using heuristics to complete this task in the minimum amount of time. As some generated grids may allow multiple solutions and require making choices to continue the resolution, I used backtracking to deal with choices leading to inconsistent solved grids. Backtracking was also used in order to generate grid with a **unique** solution. The generation consists in first filling randomly a grid to a solved grid, then blanking some cells randomly and try to solve the grid. If the grid has more than one solution while the unique option is specified, the cell is reset to its solved value and another random cell is blanked among the remaining ones. If the process take too much time, another full grid is generated and we blank random cells again.

Below is an example of utilisation of the program.

<pre>> ./sudoku --generate=25 --unique --output grid_25.txt

***** Generating grid of size 25 ...

The grid has been generated !
Initial fill ratio: 60%
This grid has a unique solution
</pre>

<pre style="font-size: 0.8em; line-height: 1.2;">> ./sudoku grid_25.txt --verbose --all 

------ SUDOKU grid (size 25) ------

2 F M 6 H P _ G D J _ E 8 4 L N _ _ 9 _ _ _ B 7 _ 
_ _ J _ D _ _ N _ _ _ 1 I 5 3 _ B E _ H 9 6 _ 2 F 
_ I G _ _ _ 5 E _ _ _ _ _ 9 _ 4 _ C 2 _ N D J _ H 
_ 3 E 5 K _ _ 9 _ 4 _ B 7 G _ J D _ P _ _ M _ _ C 
B A 9 _ _ F 3 C _ 2 D _ H P _ _ K M L 7 _ 5 O _ 8 
_ 2 _ _ I _ 4 _ _ D H P E 8 6 _ 5 _ F M _ C _ N A 
N _ 8 M B _ 6 F _ _ I 4 D _ A O L 2 1 3 J E G 5 _ 
1 H A _ _ _ 8 J _ I 5 M 3 L C _ _ _ G B 7 F K 6 _ 
_ _ 6 J O E _ 3 9 M 1 F G B K 8 _ _ D _ 2 L I _ P 
E _ _ 3 F _ L 1 _ P 9 _ 2 _ N _ H _ I _ _ 8 D B 4 
3 _ _ A G N _ _ 1 _ _ D _ K M L J O E _ _ I C F _ 
_ O _ _ 6 K _ _ G _ L 8 _ E _ _ N _ _ 4 D P _ M 1 
_ N _ _ _ B 2 5 _ E 3 G _ _ _ _ 9 D 6 _ O _ 7 _ _ 
5 1 _ L _ H D O F 6 7 9 J _ _ M P 8 _ C B _ _ _ _ 
_ 7 K _ _ _ P _ _ L _ _ 1 O _ _ F A B _ _ _ 8 E _ 
6 8 _ G 2 5 _ A B 9 P _ K 3 1 F M I N L _ O _ C _ 
A B 4 H _ D _ _ 8 F _ _ _ _ _ 6 O G J _ 3 9 _ _ M 
C K N _ _ I O L 6 H 8 A M F _ D 1 _ 4 2 G _ P _ 7 
9 J _ _ _ M N 4 K 3 O L _ _ _ 5 _ B C _ I _ 2 8 D 
O M 7 _ 3 J G _ _ 1 B _ _ _ _ A _ 9 H _ _ K 6 L _ 
_ _ _ _ 4 _ E H _ _ K _ 9 I _ 7 6 _ _ _ _ _ _ A _ 
_ _ 3 F _ 1 _ D L _ _ 2 _ _ 8 _ A 4 _ _ C 7 _ 9 J 
H D _ _ J 9 _ K _ O A 3 P M _ _ G _ 8 _ _ _ L 4 B 
_ 6 _ 2 A _ M _ _ C _ H _ D F B E K _ 9 _ N _ O G 
_ 9 _ _ 8 A _ _ 3 _ 4 C O 1 7 P _ L 5 J K _ _ D I 

***** Solving grid from &apos;grid_25.txt&apos; ...

Solution 1:
2 F M 6 H P 1 G D J C E 8 4 L N I 5 9 O A 3 B 7 K 
P C J O D L K N 7 8 M 1 I 5 3 G B E A H 9 6 4 2 F 
L I G 1 7 6 5 E M B F K A 9 O 4 3 C 2 8 N D J P H 
8 3 E 5 K O H 9 A 4 N B 7 G 2 J D F P 6 L M 1 I C 
B A 9 4 N F 3 C I 2 D 6 H P J 1 K M L 7 E 5 O G 8 
7 2 L K I G 4 B O D H P E 8 6 9 5 J F M 1 C 3 N A 
N P 8 M B C 6 F H K I 4 D 7 A O L 2 1 3 J E G 5 9 
1 H A D 9 2 8 J N I 5 M 3 L C E 4 P G B 7 F K 6 O 
4 5 6 J O E A 3 9 M 1 F G B K 8 C 7 D N 2 L I H P 
E G C 3 F 7 L 1 5 P 9 O 2 J N K H 6 I A M 8 D B 4 
3 4 P A G N 9 8 1 7 2 D B K M L J O E 5 H I C F 6 
F O 2 B 6 K J I G A L 8 C E 5 3 N H 7 4 D P 9 M 1 
J N H 8 M B 2 5 C E 3 G F A P I 9 D 6 1 O 4 7 K L 
5 1 I L E H D O F 6 7 9 J N 4 M P 8 K C B G A 3 2 
D 7 K 9 C 3 P M 4 L 6 I 1 O H 2 F A B G 5 J 8 E N 
6 8 D G 2 5 7 A B 9 P J K 3 1 F M I N L 4 O H C E 
A B 4 H L D C P 8 F E 7 5 2 I 6 O G J K 3 9 N 1 M 
C K N E 5 I O L 6 H 8 A M F 9 D 1 3 4 2 G B P J 7 
9 J F P 1 M N 4 K 3 O L 6 H G 5 7 B C E I A 2 8 D 
O M 7 I 3 J G 2 E 1 B N 4 C D A 8 9 H P F K 6 L 5 
G L O C 4 8 E H J N K 5 9 I B 7 6 1 M D P 2 F A 3 
K E 3 F P 1 B D L 5 G 2 N 6 8 H A 4 O I C 7 M 9 J 
H D 5 7 J 9 I K 2 O A 3 P M E C G N 8 F 6 1 L 4 B 
I 6 1 2 A 4 M 7 P C J H L D F B E K 3 9 8 N 5 O G 
M 9 B N 8 A F 6 3 G 4 C O 1 7 P 2 L 5 J K H E D I 

The grid is solved !

Statistics of the current run:
* Initial fill ratio:	60%
* Number of choices:	0
* Number of solutions:	1
</pre>

<!--more-->
