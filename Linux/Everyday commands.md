
### Size of folder of disk

use `-b` to get the size in bytes
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

### Get processes

```shell
pgrep [executable-name]
# then
kill [executable-id]
```