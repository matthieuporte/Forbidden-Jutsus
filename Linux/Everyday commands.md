
### Size of folder of disk

```shell
du -sh Forbidden-Jutsus/
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
tar -xvf given-files.tar
```