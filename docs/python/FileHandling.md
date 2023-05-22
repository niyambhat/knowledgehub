---
sidebar_position: 3
---

## File Handling

Imagine you are trying to come up with a name for your new dog. You're really unsure of what you'd like to call the dog, so you decide to use your Python skills to help you decide.

You start by accessing a file with a shortlist of names you'd like to use for your new pet.

The file is named petnames.txt, and has the following content:

```Python
Ace
Atlas
Bailey
Bear
Blaze
Boomer
Buddy
Coco
Cooper
Duke
Dozer
Echo
Gizmo
Harley
Mac
Max
Milo
Oscar
Rex
Rocky
Rocket
```

To do this, you'll need to have a Python file into which you'll be importing the petnames.txt file, as follows:

f = open("petnames.txt", "r")

The open() function reads in a file outside of the program itself.The open() function accepts two parameters:

* The path and the filename in the form of a string.

* The import mode (the default being "r" - which means "read")*