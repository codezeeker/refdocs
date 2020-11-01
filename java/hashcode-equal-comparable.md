contract between equal and dashcode - 

1) If two objects are equal, then they must have the same hash code.
2) If two objects have the same hash code, they may or may not be equal.


* hashcode usually return hexa value of address of that object.




equal and hashcode - for searching
compare and compareTo - for sorting



You need not to implement hascode and equals if you only want to do sorting not seraching (by verifying logical equal comparision).
