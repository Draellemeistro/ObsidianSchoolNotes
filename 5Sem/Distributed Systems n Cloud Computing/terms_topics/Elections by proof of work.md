for [[Leader Election]]
### Basics (_think [[Blockchain Architecture|Blockchain]]_)
- Consider a potentially large group of processes
- Each process is required to solve a computational puzzle 
- When a process solves the puzzle, it broadcasts its victory to the group
- We assume there is a conflict resolution procedure when more than one process claims victory
### Solving a computational puzzle
![[image_Leader Election.png]]
##### Controlled race
![[image_Leader Election-1.png]]
#### Observation
![[image_Leader Election-2.png]]