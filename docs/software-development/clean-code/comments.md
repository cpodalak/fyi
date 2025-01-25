---
slug: comments
title: Comments
tags: [clean-code]
sidebar_position: 5
---

While comments can be incredibly useful, they can also clutter your code if not used wisely. Often reviewers overlook comments as they seem to ease their review job.

### TL;DR
> - If you find yourself needing to write many comments, it may indicate poor design. Consider refactoring the code instead.
> - Write self-explanatory code; comments should explain why, not what. 
> - Use comments judiciously for complex logic, design choices, warnings, or legal notices. 
> - Avoid redundant, misleading, or outdated comments; remove commented-out code. 
> - Keep comments concise and relevant to the immediately surrounding code.

## Different commenting styles
### When Code isn't enough
There are times when code alone cannot fully convey the intent or reasoning behind a decision.

```
# Check to see if the employee is eligible for full benefits
if (employee.flags & HOURLY_FLAG) and (employee.age > 65):
```

This comment is useful, but the code can be made more self-explanatory:

```
if employee.is_eligible_for_full_benefits():
```

### Legal Comments
These comments are essential, but they should refer to standard licenses or documents rather than including lengthy legal text within the code.
```
# Copyright (C) 2023 by Your Company. All rights reserved.
# Released under the terms of the GNU General Public License.
```

### Informative Comments
Informative comments can clarify code where a function name might not suffice:
```
# Returns an instance of the Responder being tested.
def responder_instance():
    pass
```
In this case, renaming the function to responder_being_tested might eliminate the need for the comment.


### Explanation of Intent
Sometimes a comment provides insight into the reasoning behind a decision:

```
# Sort this class higher than others to prioritize processing
```
This type of comment can be invaluable, especially when it documents a non-obvious decision.

### Warning of Consequences
Comments that warn of potential consequences can be beneficial. Such comments alert developers to tread carefully when modifying the code.
```
# Warning: This function modifies the global state.
```

### TODO Comments
TODO comments can be useful reminders. However, they should not be an excuse for leaving poor code in the system indefinitely.

```
# Refactor this function to improve performance
```

### Redundant Comments
Comments that restate what is obvious in the code are unnecessary. The code is self-explanatory, and the comment adds no value.
```
# Increment the counter by 1
counter += 1
```

### Misleading Comments
Comments that are not precise can lead to confusion. Here, the comment is misleading as it doesn't specify the sorting order.
```
# This function does X
def do_x():
    pass
```

### Commented Out Code
Commenting out code instead of removing it can lead to clutter. 
```
# response.setContent(reader.read(formatter.getByteCount()))
```

### Noise Comments
Avoid comments that add no information:
```
# Default constructor
def __init__(self):
    pass
```
### Non local Comments
Comments should be relevant to the code they accompany.
```
# Default port is 8080
def connect_to_server():
    pass
```