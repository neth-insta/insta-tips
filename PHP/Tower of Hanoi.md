# Tower of Hanoi
The Tower of Hanoi (a.k.a Tower of Brahma and Lucas' Tower) is a mathematical game or puzzle. 
The objective of the puzzle is to move the entire stack to another rod, obeying the following simple rules:
1.  Move only one disk at a time.
1. A larger disk may not be placed ontop of a smaller disk.
1. All disks, except the one being moved, must be on a peg. 
```php
function tower_of_hanoi($diskCount, $fromPole, $toPole, $viaPole)
{
 if ($diskCount == 1)
 {
  echo "Move disk from pole " . $fromPole . " to pole " . $toPole . "
";
 }
 else
 {
  tower_of_hanoi($diskCount - 1, $fromPole, $viaPole, $toPole);
  tower_of_hanoi(1, $fromPole, $toPole, $viaPole);
  tower_of_hanoi($diskCount - 1, $viaPole, $toPole, $fromPole);
 }
}
//example
tower_of_hanoi(4, 1, 2, 3);
```
