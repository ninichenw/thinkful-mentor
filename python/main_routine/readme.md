## What does `if __name__ == “__main__”:` do?

Basically all modules have an implicit filename called `__main__`, so `__name__` will be equal to `__main__` when you run the module from the command line. There's a bit of black magic happening. Let's look at an example.

### Create two new files:

first.py:
```python    
# first.py

if __name__ == '__main__':
  print('This print statement is ran from the current module.')
else:
  print('This print statement is ran from a different module.')
```

second.py:
```python
#second.py

import first
```
        
### Now run the files:

```
$ python first.py
This print statement is ran from the current module.

$ python second.py
This print statement is ran from a different module
```

### What's going on?

Behind the scenes, the `__name__` variable is set equal to `"__main__"`, indicating that we're running the statements in the current file rather than importing it. So the first file runs the code within the current module, while the second file imports the code from the first.





