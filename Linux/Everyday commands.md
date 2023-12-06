
### Size of folder of disk

use `-b` to get the size in bytes
```shell
du -sh Forbidden-Jutsus/
```

### Nb of files in dir

```shell
ls -1 | wc -l
```

### Download files from server

```shell
#! /bin/bash

for i in {1..40}
do
	$(printf "wget https://pi.math.cornell.edu/~andreim/Lec%d.pdf\n" $i)
done

```

### Untar

```shell
tar -xvaf given-files.tar.gz
```

`-x` is for **extract**
`-v` is for **verbose**
`-a` is for **auto-compress**
`-f` is for **file**

### Get processes

```shell
pgrep [executable-name]
# then
kill [executable-pid]
```

or 

```shell
ps -aux #to see all process
ps #to see your processes
```

or `htop` (ez)
