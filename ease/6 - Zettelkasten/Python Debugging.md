2025-01-18 23:48

Status:

Tags: [[python]]

# Python Debugging


### Debugging Python with `pdb`

`pdb` is the built-in Python debugger that allows you to pause your program, inspect variables, and step through the execution of your code to understand and fix issues.

#### Starting the Debugger

To start debugging, you can use `pdb.set_trace()` to set a breakpoint in your code. When the program execution reaches this point, the debugger will pause, and you'll be able to interactively inspect and control the program.

**Example:**

```python
import pdb

def seq(n):
    for i in range(n):
        pdb.set_trace()  # breakpoint
        print(i)
    return

seq(5)
```

When the program reaches `pdb.set_trace()`, it will pause and allow you to enter commands in the interactive debugger.

#### Debugger Commands

Here are some of the commonly used commands in `pdb`:

1. **`h(elp)` [command]**
    
    - Without an argument: Displays the list of available commands.
    - With a command as an argument: Provides help on that specific command.  
        Example:
    
    ```python
    help pdb
    ```
    
2. **`w(here)`**
    
    - Prints the stack trace with the most recent frame at the bottom. An arrow indicates the current frame.
3. **`d(own)` [count]**
    
    - Moves down in the stack trace by the specified count (default is 1). This lets you view newer frames.
4. **`c(ont(inue))`**
    
    - Resumes program execution and stops only when another breakpoint is hit.
5. **`q(uit)`**
    
    - Exits the debugger and terminates the program.

#### Example Debugging Session

For the code:

```python
import pdb

def seq(n):
    for i in range(n):
        pdb.set_trace()  # breakpoint
        print(i)
    return

seq(5)
```

When you run the code, the debugger will pause at the breakpoint for each iteration of the loop. You can use commands like `w`, `d`, `c`, or `q` to inspect the stack trace, move through the code, or continue execution.

# References