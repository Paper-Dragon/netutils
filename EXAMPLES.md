# Examples

List of examples:

| Category | Example title |
|----------|---------------|
| Performance | Network performance between two points |
| Performance | Connectivity to a database via JDBC |
| Monitoring | Monitors network usage |
| Monitoring | Monitor Java memory |

> To search for a specific example type '/Network performance<ENTER>' and use the arrow keys to navigate

---

## 🏎️  Network performance between two points

To obtain the transfer rate, bandwidth and error ratio transmiting from point B to point A, on point A execute:

```bash
iperf -s -p 12345
```

And on point B execute:

```bash
iperf -c a.point.net.local -p 12345 -e --trip-times
```

> Check point A output for latency results

---

## 🏎️  Connectivity to a database via JDBC

You can test connectivity to a PostgreSQL, H2 and Oracle databases without any extra driver. 

1. Set the database password securely

```bash
read -sp "Password: " PASS && export PASS && echo
```

2. Execute for the target database JDBC and user

```bash
jdbc.yaml jdbc=jdbc:postgresql://hh-pgsql-public.ebi.ac.uk:5432/pfmegrnargs user=reader pass=$PASS
```

> To check more options just execute ```jdbc.yaml```

---

## 🔍 Monitors network usage

To monitor the network usage, and bandwidth, on a specific network device (e.g. eth0), execute:

```bash
sudo iftop -i eth0 -P
```

---

## 🔍 Monitor Java memory

This is possible by starting a debug container for an existing Kubernetes pod where a Java application is running (execute 'usage-help' to get more details on how to start a Kubernetes debug container).

In the debugger container identify the running Java process:

```bash
ps -axf
```

> PIDs are "shared" between the target container and the debug container

After identifying the Java pid of the target container execute a similar command changing the HSPERF variable value (the example is assuming pid 12 running under "myuser"):

```bash
HSPERF=/proc/12/root/tmp/hsperfdata_myuser/12 && oafp $HSPERF in=hsperf path=java out=grid grid="[[(title:Threads,type:chart,obj:'int threads.live:green:live threads.livePeak:red:peak threads.daemon:blue:daemon -min:0')|(title:Class Loaders,type:chart,obj:'int cls.loadedClasses:blue:loaded cls.unloadedClasses:red:unloaded')]|[(title:Heap,type:chart,obj:'bytes __mem.total:red:total __mem.used:blue:used -min:0')|(title:Metaspace,type:chart,obj:'bytes __mem.metaTotal:blue:total __mem.metaUsed:green:used -min:0')]]" loop=1
```

You can also check a more complete dashboard with:

```bash
javaGC.yaml file=/proc/12/root/tmp/hsperfdata_myuser/12
```