# Nimiq-GPU-Miner-NoncerPro-GPU-miner
Nimiq GPU Miner NoncerPro NoncerPro is a powreful GPU miner with local statistics API and is compatible with HiveOS.

Nimiq GPU miner for Nvidia graphic cards.
This is the first Nimiq GPU miner that utilizes the standard Nano mining protocol and is compatible with all of the available nimiq pools.

Options
  Options:
  -a, --address         Nimiq wallet address                 [string] [required]
  -n, --name            Device name                                     [string]
  -s, --server          Pool server address
                        multiple addresses or a single string
                        Example: -s=eu.nimpool.io us.nimiqpocket.com
                        Default: eu.nimpool.io                           [array]
  -p, --port            Pool server port
                        Default: 8444                                    [array]
  -m, --mode            Mining mode
                        Can be dumb or nano
                        Default: nano                                   [string]
  -d, --devices         Active GPUs
                        Example: -d=0 1 3
                        Default: All available GPUs                      [array]
  -t, --threads         Number of threads per GPU
                        Example: -t=2 or -t=2 2 4
                        Default: 1                                       [array]
  -b, --batchsize       batchsize per thread.
                        Example: -b=100 or -b=100 120 200
                        Default: auto based on available device memory   [array]
  -i, --api             Enable/Disable API
                        Default: Enable                                [boolean]
  -o, --apiport         API port
                        Default: 3000                                   [number]
  --diff, --difficulty  Start difficulty
                        Default: Disabled                               [number]
  -h, --help            Show help                                      [boolean]
  -v, --version         Show version number                            [boolean]
Config file
In addition to the above command line options, there is a miner.conf file which has the exact same options. If you uncomment any config option, it will be used as the default value for that option in the next run. Config options can still be overridden by command line options.

Requirements
Binary packages have been built with CUDA 10.0. You need to update your driver to the latest version in order to use them.

The minimum supported Compute Capability is SM3.5. You can check your cards' SM support in the following link: https://developer.nvidia.com/cuda-gpus

If you are using Windows, the minimum virtual memory must be set to the total amount of allocated gpu memory. So if you have 6 x 1080 tis and want to use 8GB on each card, you will need 48 GB of virtual memory. This only applies to Windows.

If you are running the noncerpro.exe file directly, make sure you have set UV_THREADPOOL_SIZE to atleast 32;

Usage
Download the binary packge for Windows/Linux, edit mine.bat/mine.sh file and insert your own wallet address and run it.

You can control the amount of memory allocation per thread by using --batchsize option. Here is how it works:

re my best parameters for 1080 ti on Linux and Windows:

Linux: --threads=4 --batchsize=50
Windows: --threads=2 --batchsize=92