# A Kernel Seedling
This linux kernel (when inserted) creates a file at the location /proc/count which will contain the amount of currently running processes on your computer.

## Building
```shell
-- command for build --
make
```

## Running
```shell
-- command for running binary --
sudo insmod proc_count.ko && cat /proc/count

this command inserts the module and outputs whatever is stored in /proc/count which will show the amount of currently running processes
```
-- results --
outputs the current amount of processes running on your device

## Cleaning Up
```shell
-- command for cleaning up binary --
sudo rmmod proc_count.ko && make clean

this command removes the module from your linux system and then uses the make file to clean up the rest
```

## Testing
```python
python -m unittest
```
-- results --
outputs which tests the kernel module passes/fails, these are confirmed using linux commands, eg "ps aux | wc -l"

Report which kernel release version you tested your module on
(hint: use `uname`, check for options with `man uname`).
It should match release numbers as seen on https://www.kernel.org/.

```shell
uname -r -s -v
```
-r: (Release) 5.14.8-arch1-1
-s: (Name) Linux
-v: (Version) #1 SMP PREEMPT Sun, 26, Sep 2021 19:36:15 +0000