## Powerful linux
 _My own linux helper_
 
## Detect Linux Distro

Using `uname`
```sh
> uname -a
Darwin MacBook-Pro-Pawe.local 19.6.0 Darwin Kernel Version 19.6.0: Thu Oct 29 22:56:45 PDT 2020; root:xnu-6153.141.2.2~1/RELEASE_X86_64 x86_64
```

Using `cat`
```sh
> cat /etc/*release
SUSE LINUX Enterprise Server 9 (i586)
VERSION = 9
PATCHLEVEL = 3

> cat /etc/issue
Welcome to SUSE LINUX Enterprise Server 9 (i586) - Kernel \r (\l).
```


## Loops in bash

FOR
```sh
#!/bin/bash
echo "Bash version ${BASH_VERSION}..."
for i in {0..10..2}; do 
     echo "Welcome $i times"
done
```

```sh
#!/bin/bash
for (( c=1; c<=5; c++ )); do  
   echo "Welcome $c times"
done
```
```sh
#!/bin/bash
for file in /etc/*
do
	if [ "${file}" == "/etc/resolv.conf" ]
	then
		countNameservers=$(grep -c nameserver /etc/resolv.conf)
		echo "Total  ${countNameservers} nameservers defined in ${file}"
		break
	fi
done
```

## IF in bash
`[]` is referens to `test`

| Operator | Description |
| ------ | ------ |
| ! EXPRESSION | The EXPRESSION is false. |
| -n STRING | The length of STRING is greater than zero. |
| -z STRING | The lengh of STRING is zero (ie it is empty). |
| STRING1 = STRING2 | STRING1 is equal to STRING2 |
| STRING1 != STRING2 | STRING1 is not equal to STRING2 |
| INTEGER1 -eq INTEGER2 | INTEGER1 is numerically equal to INTEGER2 |
| INTEGER1 -gt INTEGER2 | INTEGER1 is numerically greater than INTEGER2 |
| INTEGER1 -lt INTEGER2 | INTEGER1 is numerically less than INTEGER2 |
| -d FILE | FILE exists and is a directory. |
| -e FILE | FILE exists. |
| -r FILE | FILE exists and the read permission is granted. |
| -s FILE | FILE exists and it's size is greater than zero (File it is not empty). |
| -w FILE | FILE exists and the write permission is granted. |
| -x FILE | FILE exists and the execute permission is granted. |

```sh
#!/bin/bash
if [ <some test> ]; then
    <commands>
else
    <other commands>
fi
```

