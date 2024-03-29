1. **paramiko** is a library, provides support for SSH protocol, allowing you to perform various operation such as connecting to remote servers, executing commands, transferring files, and managing SSH keys programmatically from within your Python code.


2. newIndict function:
```
for key in mapList[:-1]:
    dataDict = dataDict.setdefault(key,{})
```
-> Explain:
    - The **'{}'** represents an empty dictionary that serves as the default value if the **'key'** not found in **'dataDict'**.
    - Here's how the code works: If the **'key'** is already present in **'dataDict'**, **'setdefault'** returns the corresponding value associated with that key, leaving **'dataDict'** unchanged. If the **'key'** is not present in **'dataDict'**, **'setDefault'** inserts the key-value pair **'{key:{}}'** into **'dataDict'** and returns **'{}'**, effectively creating a new nested dictionary at the specified key.
    - By using **'{}'** as the default value in **'setdefault'**, this code ensures that if a key in **'mapList[:-1]'** is not found in **'dataDict'**, a new empty dictionary will be created at that key, allowing for smooth navigation through nested dictionaries based on the keys provided in **mapList**.
    
