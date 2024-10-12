# Week 4 and Week 5 Assignments

## Week 4 - Happy Number Code

For Week 4, we implemented a Python function to check if a number is a 'Happy Number'.

### Code:

```python
def isHappy(n: int):
    def get_next(num):
        total_sum = 0
        while num > 0:
            digit = num % 10
            total_sum += digit ** 2
            num //= 10
        return total_sum

    seen = set()
    while n != 1 and n not in seen:
        seen.add(n)
        n = get_next(n)
    
    return n == 1

# User input
user_input = int(input("Enter a number to check if it's a happy number: "))
if isHappy(user_input):
    print(f"{user_input} is a happy number!")
else:
    print(f"{user_input} is not a happy number.")
```

### Explanation:

The function `isHappy(n)` determines whether a number is a "happy number." A happy number is defined by the following process: starting with any positive integer, replace the number by the sum of the squares of its digits. Repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. Those numbers for which this process ends in 1 are happy numbers. The algorithm keeps track of seen numbers to avoid infinite loops.

### Sample Output:

- Input: 19
- Output: 19 is a happy number!
  
- Input: 4
- Output: 4 is not a happy number!

---

## Week 5 - Docker Commands

For Week 5, we explored several Docker commands to inspect and manage containers.

### Command 1: `docker exec <your container> cat /etc/os-release`

This command displays the operating system information of the container. The file `/etc/os-release` contains system identification data. The command outputs details like the OS name, version, and ID.

### Command 2: `docker exec <your container> git --version`

This command checks the version of Git installed in the container. Git is a widely-used version control system.

### Command 3: `docker exec <your container> python3 --version`

This command checks the version of Python installed in the container. Python is a popular programming language, and this command ensures that Python3 is available and correctly installed.

### Command 4: `docker inspect --format="{{ .HostConfig.Binds }}" <container_name>`

This command inspects the Docker container and shows the bind mounts that have been set up. Bind mounts are used to mount directories from the host machine to the container, allowing data persistence or access to specific directories.

---
