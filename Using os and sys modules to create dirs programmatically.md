```py
#!/home/fatboyrus/miniconda3/bin/python3
import os
import sys

os.mkdir(f'{os.getcwd()}/{sys.argv[1]}')
for i in range(int(sys.argv[2])):
    os.mkdir(f'{os.getcwd()}/{sys.argv[1]}/{i}')
```
Pass in the commands below to create a new dir with 3 sub dirs.
```
./exp.py batch_rus 3
```
