# Python Requirements Checking
Utility to check if the dependency version are in-sync.

## What's this for?
If you have a big python project with multiple python modules, and you want to enforce all the dependencies they are using to be on the same version, this is the tool for you!

## Usage
Given the following to requirements.txt file:

*requirements-1.txt*
```
pygame==2.0.0
```

*requirements-2.txt*
```
pygame==2.0.1
```

*requirements-3.txt*
```
pygame==2.0.1
```

### Mismatch:
Use 
```
python check_dependency.py requirements-1.txt requirements-2.txt
```
It will output and return a **255** return code:
```
Mismatch dependency for pygame at file requirements-2.txt, ==2.0.1 is not ==2.0.0
```

### Matches:
Use
```
python check_dependency.py requirements-2.txt requirements-3.txt
```
Exits with no console output and a return code of **0**.

## Notes:
- This script handles `==`, `>=`, `>`, `<=`, `<`, `~=` version specifiers, but provides no means of validation.
- This script detects versioning coherency through direct string comparison instead of version resolution.
