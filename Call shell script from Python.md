```sh
#!/bin/sh

N=0
while [ $N -le 11 ]
do
        echo "$N"
        N=`expr $N + 1`
done
```

```py
#!/home/fatguyrus/miniconda3/bin/python3
import os

os.system('sh bsh.sh')
```
