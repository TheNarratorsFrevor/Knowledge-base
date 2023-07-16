
Nigel's Monitor (`nmon`) is a system performance monitoring tool originally developed by IBM for the [[AIX operating system]] and later ported for Linux on several CPU architectures.
The main benefit of `nmon` is that it allows you to monitor different aspects of your system, such as CPU utilization, memory, disk busy, network utilization, and more, in a single, concise view. Without `nmon`, you have to use specialized monitoring tools like `top` for processes, `iostat` for disks, and `ifstat` for the network to monitor various resources. Each of them presents the data differently.

## Use nmon interactively

With the applications installed, you can monitor your system interactively by running `nmon`. You're presented with an initial screen containing system information and a little help menu, displaying which keys you can press to toggle different metrics:

```bash
$ nmon

┌─16k──[H for help]──Hostname=f35ks01─Refresh= 2secs ─18:04:27────┐
│                                                                 │
│------------------------------                                   │
│ _ __  _ __ ___   ___  _ __    For help type H or ...            │
│| '_ \| '_ ` _ \ / _ \| '_ \    nmon -?  - hint                  │
│| | | | | | | | | (_) | | | |   nmon -h  - full details          │
│|_| |_|_| |_| |_|\___/|_| |_|                                    │
│                               To stop nmon type q to Quit       │
│------------------------------                                   │
│                                                                 │
│Fedora release 35 (Thirty Five) VERSION="35 (Thirty Five)"       │
│Vendor=AuthenticAMD Model=AMD EPYC-Milan Processor               │
│MHz=1911.004 bogomips=3822.00     lscpu:CPU=4 Little Endian      │
│ProcessorChips=4 PhysicalCores=1        Sockets=4 Cores=1 Thrds=1│
│                 VirtualCPUs =4         MHz=0 max=0 min=0        │
│                                                                 │
│Use these keys to toggle statistics on/off:                      │
│  c = CPU         l = CPU Long-term     - = Faster screen updates│
│  C = " WideView  U = Utilisation       + = Slower screen updates│
│  m = Memory      V = Virtual memory    j = File Systems         │
│  d = Disks       n = Network           . = only busy disks/procs│
│  r = Resource    N = NFS               h = more options         │
│  k = Kernel      t = Top-processes     q = Quit                 │
│─────────────────────────────────────────────────────────────────│
```
