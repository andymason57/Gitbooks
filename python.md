# Python

## Gitbooks
Repository to store Gitbooks

**git remote add origin** url


##Lists

 
**Insert method**

list.insert(position, value) - insert value into list.


**Delete statement**

del list[index]

**pop() method**

Removes last item from list

list.pop() 
 


# useful tips : 

Equivalent of FileNotFoundError (Python3) in Python 2 is 

try:
  ...
 except EnvironmentError as e: 
    print(os.strerror(e.errno))