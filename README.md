# Collections
## This python code is written to sort the the number of connections from an IP in the access log using the "collections" module,


```python
import os
import logparser
import collections 

    
logFile = 'access.log'    
        
ipCounter = collections.Counter()

        
with open(logFile,'r') as fh:
    
    for logLine in fh:
      
        ip = logparser.parser(logLine)['host'] 
        
        ipCounter.update([ip])
        
for item in ipCounter:
    print('{:30} {}'.format(item, ipCounter[item]))
```
