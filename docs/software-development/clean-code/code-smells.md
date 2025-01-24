---
slug: code-smells
title: Code Smells
sidebar_position: 25
---

# Code Smells
Code Smells from *"Clean Code: A Handbook of Agile Software Craftsmanship - Robert C.Martin"*

## Comments
**C1: Inappropriate information** - Comments that add no value or are irrelevant to the code.  
    `// TODO: Something cool here someday`

**C2: Obsolete information** - Comments that are outdated and no longer reflect the current code.  
    `// This function calculates tax (now it validates input)`

**C3: Redundant comment** - Comments that repeat what the code already clearly states.
```
x = x + 1  # Increment x by 1
```

**C4: Poorly written comment**  - Comments that are hard to understand due to bad grammar or structure.  
   `// increment x somehow`

**C5: Commented-out code** - Code that is commented out and left in the source.  
```
    # x = calculate_tax()
```

## Environment
**E1: Build requires more than one step** - Build process is complex and not automated.  
    `Run step1.sh, then build manually.`

**E2: Test requires more than one step** - Testing is not automated or involves manual steps.  
    `Run tests in IDE and verify logs manually.`

## Functions
**F1: Too many arguments** - Functions have more than a reasonable number of parameters.  
    `def calculate(a, b, c, d, e, f): pass`

**F2: Too many outputs** - Functions return too many results.  
    `def process(): return a, b, c, d`

**F3: Flat arguments** - Passing unstructured data instead of objects.  
    `def draw(x1, y1, x2, y2): pass`

**F4: Dead functions** - Unused functions left in the codebase.  
    `def old_logic(): pass  # Not called anywhere`

## Generic
**G1: Multiple languages in one source file** - Mixing different programming languages in the same file. HTML with embedded PHP and JavaScript.

**G2: Obvious behavior is unimplemented** - Expected behavior is missing.  

**G3: Incorrect behavior at boundaries** - Edge cases are not handled properly.  
    `def divide(a, b): return a / b  # Crashes for b=0`

**G4: Overridden safeties** - Ignoring safety mechanisms.
    `disable_security_checks = True`

**G5: Duplication** - Repeated code instead of reusing functions.  
```
if x > 0: print("Positive")
if x == 0: print("Zero")
```

**G6: Code at wrong level of abstraction** - Logic misplaced in a layer of unrelated functionality. Database queries in the UI layer.

**G7: Base class depending on its derivatives** - A parent class depends on or knows about its child classes.  

**G8: Overloaded objects** - Overloaded objects or functions with too many responsibilities.  
```
class Employee:
    def get_salary(self): pass
    def calculate_tax(self): pass
    def save_to_database(self): pass
```

**G9: Dead code** - Code that is no longer used but still exists in the source.  

**G10: Vertical separation** -  Related code is placed far apart, making understanding difficult. Defining variables at the top and their usage deep in the file.

**G11: Inconsistency** -  Lack of uniformity in code style or conventions. Using both `snake_case` and `camelCase` in the same file.

**G12: Clutter** -  Excessive or unnecessary details that obscure functionality. Comments or logs flooding the codebase.

**G13: Artificial coupling** -  Unnecessary dependencies between classes or modules. A utility class depending on business logic.

```
def calculate_area(rectangle):
    return rectangle.width * rectangle.height
```

**G15: Selector Arguments** -  Passing flags to dictate a function's behavior.
`def process_data(data, is_test=False): pass`

**G16: Obscured intent** -  Code that is unclear or lacks self-explanation.  
`def x(): return y * z`

**G17: Misplaced responsibility** -  Logic placed in an unrelated class or function. A "Logger" class managing database connections.

**G18: Inappropriate static** -  Misuse of static variables or methods.  

**G19: Use of explanatory variables** -  Replacing magic numbers with descriptive variables.  
`max_length = 10`

**G20: Function name doesn’t say what they do** -  Poorly named functions that obscure their purpose.
`def do_stuff(): pass`

**G21: Funny algorithms** -  Non-standard, unnecessarily complex implementations. Using recursion instead of iteration for simple loops.

**G22: Logical dependency** -  Implicit assumptions between unrelated components. Assuming a variable is always initialized elsewhere.

**G23: Incorrect use of if/else or switch instead of polymorphism** -  Using conditionals where object-oriented principles would suffice.  
 
```
if shape == "circle":
    draw_circle()
elif shape == "square":
    draw_square()
```

**G24: Lack of standard coding convention** -  Not adhering to a consistent coding standard. Different indentation or spacing styles in the same project.

**G25: Use of magic numbers** -  Using hard-coded values instead of constants.
`if x > 42: pass`

**G26: Not being precise** -  Ambiguous or vague logic that leads to errors. General exception catching without specificity.

**G27: Overuse of conventions instead of structured** -  Using workarounds rather than proper structure. Layering complex configuration files over logical hierarchies.

**G28: Overuse of encapsulated conditionals** -  Wrapping everything in layers of conditionals unnecessarily.
```
if x:
    if y:
        if z: pass
```

**G29: Overuse of negative conditionals** -  Too many `not` or inverted conditions.
`if not x and not y: pass`

**G30: Functions doing too many things** -  Lack of single responsibility principle. 
`def process(): validate(); save(); notify()`

**G31: Hidden temporal couplings** -  Implicit order dependencies in code. Initializing objects in the wrong order causes errors.

**G32: Structures being arbitrary** -  Disorganized structures without logical reasoning. Random grouping of unrelated classes or files.

**G33: Unencapsulated boundary conditions** -  Boundary checks scattered across the code instead of centralized.
`if x > max_limit: pass`

**G34: Functions descending more than one level of abstraction** -  Mixing high and low-level logic in the same function. Calling hardware APIs inside business logic.

**G35: Configurable data embedded in code instead of higher levels** -  Hardcoding configuration instead of externalizing it.
`max_connections = 100`

## Names
**N1: Names not being descriptive** - Poorly named variables, classes, or methods.  
`def x(): pass`

**N2: Names at different levels of abstractions** - Mixing high-level and low-level naming styles. Combining `processData` with `dataRow`.

**N3: Not using standard nomenclature wherever required** - Avoiding domain-specific or conventional terms. Using `get_data()` instead of `fetch_user()`.

**N4: Unambiguous names** - Names that can be interpreted in multiple ways. `process()` without context.

**N5: Using long names to define long scope** - Excessively long names for variables or functions.
```
def thisFunctionProcessesDataWithinDefinedScope(): pass
```

**N6: Using encoded names** - Names that rely on cryptic abbreviations or codes.  
```
def fcnCalc(): pass
```
