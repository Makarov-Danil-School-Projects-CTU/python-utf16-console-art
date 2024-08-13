Keywords: Python, Console art, Recursive

📝 Task Objective

The goal is to render a tree defined by a list of values in "UTF16-art." Each internal node of the tree always contains two items: the node's name and a list of children (not necessarily in this order). The name can be any object except a list. Example of a trivial tree with 1 node: [1, []].

📋 Example Input and Output:

Input:

[[[1, [True, ['abc', 'def']]], [2, [3.14159, 6.023e23]]], 42]

Output:

<img width="171" alt="image" src="https://github.com/user-attachments/assets/49a99923-8dae-48f2-a2d7-0586ee70d5b1">


🎨 Tree Rendering Rules:

Rendering Direction:

The tree is rendered from top to bottom, left to right.
Node Representation:

A node is represented by its name, which is the string serialization of the object defined in the node.

Indentation:

A node at depth N is indented from the left by N×{indent} characters, where {indent} is always a positive integer > 1.

Child Arrows:

If a node has K children, arrows will be drawn as follows:
To the 1st to the K-1th child, an arrow starts with the character ├ (UTF16: 0x251C).
To the Kth child, an arrow starts with the character └ (UTF16: 0x2514).

Arrow Details:

The arrow to a node's child always ends with the character > (UTF16: 0x003E; the classic "greater than" symbol).
The total length of the arrow (including the starting character and >) is always {indent}, with the filler character being the repeated character ─ (UTF16: 0x2500).

Vertical Connection:

All children of a node are connected at the arrow's starting point with a vertical line │ (UTF16: 0x2502); this is where the starting character is neither ├ nor └.

Handling Newlines in Node Names:

If a node's name contains the \n character, do not indent the rest of the name after this character.

Line Termination:

Each line is terminated with the newline character \n.

⚠️ Additional Requirements:
For invalid input, the implementation must raise an exception: raise Exception('Invalid tree').
Ensure the code style is compliant with PEP8 (you may ignore the line length requirement - C0301 and use single-letter variables in justified cases - C0103).
Test this using pylint --disable=C0301,C0103 trees.py.
Use only built-in methods (i.e., no importing of additional modules).
