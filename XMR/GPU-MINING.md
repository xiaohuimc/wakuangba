# NVIDIA GPU

XMRig 是高性能门罗币（XMR）N卡挖矿工具，支持Windows。

这是NVIDIA GPU挖掘版，还有CPU版和AMD GPU版。

⚠️GPU自动配置的建议值可能不是最佳或不起作用，您可能需要调整线程选项。如果自动配置提示错误值，请随意打开问题。

![](https://camo.githubusercontent.com/8daca1246fc9a96d5a0fff0c9ccfa16239986832/68747470733a2f2f692e696d6775722e636f6d2f7752435a33494a2e706e67)



## 特征

- 高性能。
- 官方Windows支持。
- 支持备份（故障转移）挖掘服务器。
- CryptoNight-Lite支持AEON。
- 自动GPU配置。
- GPU运行状况监控（时钟，功率，温度，风扇速度）
- Nicehash支持。

## 下载

- 二进制版本：[https://github.com/xmrig/xmrig-nvidia/releases](https://github.com/xmrig/xmrig-nvidia/releases)



## 用法

使用[config.xmrig.com](https://config.xmrig.com/nvidia)生成，编辑或共享配置。

### 命令行选项

```
-a, --algo=ALGO          specify the algorithm to use
                             cryptonight
                             cryptonight-lite
                             cryptonight-heavy
  -o, --url=URL             URL of mining server
  -O, --userpass=U:P        username:password pair for mining server
  -u, --user=USERNAME       username for mining server
  -p, --pass=PASSWORD       password for mining server
      --rig-id=ID           rig identifier for pool-side statistics (needs pool support)
  -k, --keepalive           send keepalived packet for prevent timeout (needs pool support)
      --nicehash            enable nicehash.com support
      --tls                 enable SSL/TLS support (needs pool support)
      --tls-fingerprint=F   pool TLS certificate fingerprint, if set enable strict certificate pinning
  -r, --retries=N           number of times to retry before switch to backup server (default: 5)
  -R, --retry-pause=N       time to pause between retries (default: 5)
      --cuda-devices=N      list of CUDA devices to use.
      --cuda-launch=TxB     list of launch config for the CryptoNight kernel
      --cuda-max-threads=N  limit maximum count of GPU threads in automatic mode
      --cuda-bfactor=[0-12] run CryptoNight core kernel in smaller pieces
      --cuda-bsleep=N       insert a delay of N microseconds between kernel launches
      --cuda-affinity=N     affine GPU threads to a CPU
      --no-color            disable colored output
      --variant             algorithm PoW variant
      --donate-level=N      donate level, default 5% (5 minutes in 100 minutes)
      --user-agent          set custom user-agent string for pool
  -B, --background          run the miner in the background
  -c, --config=FILE         load a JSON-format configuration file
  -l, --log-file=FILE       log all output to a file
  -S, --syslog              use system log for output messages
      --print-time=N        print hashrate report every N seconds
      --api-port=N          port for the miner API
      --api-access-token=T  access token for API
      --api-worker-id=ID    custom worker-id for API
      --api-id=ID           custom instance ID for API
      --api-ipv6            enable IPv6 support for API
      --api-no-restricted   enable full remote access (only if API token set)
      --dry-run             test configuration and exit
  -h, --help                display this help and exit
  -V, --version             output version information and exit
```



# AMD GPU

XMRig是高性能的Monero（XMR）OpenCL挖掘机，具有官方完整的Windows支持。

- 这是AMD（OpenCL）GPU挖掘版，还有一个[CPU版](https://github.com/xmrig/xmrig)和[NVIDIA GPU版](https://github.com/xmrig/xmrig-nvidia)。

⚠️GPU自动配置的建议值可能不是最佳或不起作用，您可能需要调整线程选项。

[![img](https://camo.githubusercontent.com/9f9a8b36efa7e8bb8252809aca5a70e63ab61a07/68747470733a2f2f786d7269672e636f6d2f6173736574732f696d672f73637265656e73686f74732f786d7269672d616d642d322e382e362e706e67)](https://camo.githubusercontent.com/9f9a8b36efa7e8bb8252809aca5a70e63ab61a07/68747470733a2f2f786d7269672e636f6d2f6173736574732f696d672f73637265656e73686f74732f786d7269672d616d642d322e382e362e706e67)



## 特征

- 高性能。
- 官方Windows支持。
- 支持备份（故障转移）挖掘服务器。
- CryptoNight-Lite支持AEON。
- 自动GPU配置。
- Nicehash支持。
- 它是开源软件。

## 用法

使用[config.xmrig.com](https://config.xmrig.com/amd)生成，编辑或共享配置。

### 命令行选项

```
-a, --algo=ALGO              specify the algorithm to use
                                 cryptonight
                                 cryptonight-lite
                                 cryptonight-heavy
  -o, --url=URL                URL of mining server
  -O, --userpass=U:P           username:password pair for mining server
  -u, --user=USERNAME          username for mining server
  -p, --pass=PASSWORD          password for mining server
      --rig-id=ID              rig identifier for pool-side statistics (needs pool support)
  -k, --keepalive              send keepalived for prevent timeout (needs pool support)
      --nicehash               enable nicehash.com support
      --tls                    enable SSL/TLS support (needs pool support)
      --tls-fingerprint=F      pool TLS certificate fingerprint, if set enable strict certificate pinning
  -r, --retries=N              number of times to retry before switch to backup server (default: 5)
  -R, --retry-pause=N          time to pause between retries (default: 5)
      --opencl-devices=N       list of OpenCL devices to use.
      --opencl-launch=IxW      list of launch config, intensity and worksize
      --opencl-strided-index=N list of strided_index option values for each thread
      --opencl-mem-chunk=N     list of mem_chunk option values for each thread
      --opencl-comp-mode=N     list of comp_mode option values for each thread
      --opencl-affinity=N      list of affinity GPU threads to a CPU
      --opencl-platform=N      OpenCL platform index
      --opencl-loader=N        path to OpenCL-ICD-Loader (OpenCL.dll or libOpenCL.so)
      --print-platforms        print available OpenCL platforms and exit
      --no-cache               disable OpenCL cache
      --no-color               disable colored output
      --variant                algorithm PoW variant
      --donate-level=N         donate level, default 5% (5 minutes in 100 minutes)
      --user-agent             set custom user-agent string for pool
  -B, --background             run the miner in the background
  -c, --config=FILE            load a JSON-format configuration file
  -l, --log-file=FILE          log all output to a file
  -S, --syslog                 use system log for output messages
      --print-time=N           print hashrate report every N seconds
      --api-port=N             port for the miner API
      --api-access-token=T     access token for API
      --api-worker-id=ID       custom worker-id for API
      --api-id=ID              custom instance ID for API
      --api-ipv6               enable IPv6 support for API
      --api-no-restricted      enable full remote access (only if API token set)
      --dry-run                test configuration and exit
  -h, --help                   display this help and exit
  -V, --version                output version information and exit
```