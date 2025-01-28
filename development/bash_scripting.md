## BASH Scripting Basics
### Setup the Shell Path
``` BASH
#!/bin/bash
```

### Give Script Execute Permission
```BASH
chmod u scriptname
```

### Run Script
```BASH
./scriptname.sh
```

## Conditional Statements
### IF / ELSE IF / ELSE
``` BASH
if [ condition ] then
    command1
elif [ condition ] then
    command2
else
    command3
fi
```

## Loops
### FOR Loops
``` BASH
for [arg] in [list];
do
    command1
done
```

### WHILE Loops
``` BASH
while [condition];
do
    command1
done
```