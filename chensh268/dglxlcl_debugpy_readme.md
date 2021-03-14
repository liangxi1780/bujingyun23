# debugpy - a debugger for Python

[![Build Status](https://dev.azure.com/debugpy/debugpy/_apis/build/status/debugpy-test-automation?branchName=master)](https://dev.azure.com/debugpy/debugpy/_build/latest?definitionId=1&branchName=master)
[![GitHub](https://img.shields.io/badge/license-MIT-brightgreen.svg)](https://raw.githubusercontent.com/microsoft/debugpy/master/LICENSE)
[![PyPI](https://img.shields.io/pypi/v/debugpy.svg)](https://pypi.org/project/debugpy/)
[![PyPI](https://img.shields.io/pypi/pyversions/debugpy.svg)](https://pypi.org/project/debugpy/)

#### Coverage

| OS | Coverage |
|---|---|
| Windows | ![Azure DevOps coverage](https://img.shields.io/azure-devops/coverage/debugpy/debugpy/2) |
| Linux | ![Azure DevOps coverage](https://img.shields.io/azure-devops/coverage/debugpy/debugpy/3) |
| Mac | ![Azure DevOps coverage](https://img.shields.io/azure-devops/coverage/debugpy/debugpy/4) |

This debugger implements the Debug Adapter Protocol: [debugProtocol.json](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466da0a62e928567e22efc9994c2bad2b5424e34f5179cc12fadeaf858a577de9e66cef8ee750cf5f33c63305888c1808dd4f0747a669905021657ddd012117b6ffbef8034d12b8c4cfb468f62e19993ff)

## `debugpy` CLI Usage
### Debugging a script file
To run a script file with debugging enabled, but without waiting for the client to attach (i.e. code starts executing immediately):
```console
-m debugpy --listen localhost:5678 myfile.py
```
To wait until the client attaches before running your code, use the `--wait-for-client` switch.
```console
-m debugpy --listen localhost:5678 --wait-for-client myfile.py
```
The hostname passed to `--listen` specifies the interface on which the debug adapter will be listening for connections from DAP clients. It can be omitted, with only the port number specified:
```console
-m debugpy --listen 5678 ...
```
in which case the default interface is 127.0.0.1.

To be able to attach from another machine, make sure that the adapter is listening on a public interface - using `0.0.0.0` will make it listen on all available interfaces:
```console
-m debugpy --listen 0.0.0.0:5678 myfile.py
```
This should only be done on secure networks, since anyone who can connect to the specified port can then execute arbitrary code within the debugged process.

To pass arguments to the script, just specify them after the filename. This works the same as with Python itself - everything up to  the filename is processed by debugpy, but everything after that becomes `sys.argv` of the running process.

### Debugging a module
To run a module, use the `-m` switch instead of filename:
```console
-m debugpy --listen localhost:5678 -m mymodule
```
Same as with scripts, command line arguments can be passed to the module by specifying them after the module name. All other debugpy switches work identically in this mode; in particular, `--wait-for-client` can be used to block execution until the client attaches.

### Attaching to a running process by ID
The following command injects the debugger into a process with a given PID that is running Python code. Once the command returns, a debugpy server is running within the process, as if that process was launched via `-m debugpy` itself.
```console
-m debugpy --listen localhost:5678 --pid 12345
```

## `debugpy` Import usage
### Enabling debugging
At the beginning of your script, import debugpy, and call `debugpy.listen()` to start the debug adapter, passing a `(host, port)` tuple as the first argument.
```python
import debugpy
debugpy.listen(("localhost", 5678))
...
```
As with the `--listen` command line switch, hostname can be omitted, and defaults to `"127.0.0.1"`:
```python
debugpy.listen(5678)
...
```

### Waiting for the client to attach
Use the `debugpy.wait_for_client()` function to block program execution until the client is attached.
```python
import debugpy
debugpy.listen(5678)
debugpy.wait_for_client()  # blocks execution until client is attached
...
```

### `breakpoint()` function
In Python 3.7 and above, `debugpy` supports the standard `breakpoint()` function. Use `debugpy.breakpoint()` function for similar behavior and compatibility with older versions of Python. If the debugger is attached when either of these functions is invoked, it will pause execution on the calling line, as if it had a breakpoint set. If there's no client attached, the functions do nothing, and the code continues to execute normally.
```python
import debugpy
debugpy.listen(...)

while True:
    ...
    breakpoint()  # or debugpy.breakpoint() on 3.6 and below
    ...
```

## Debugger logging

To enable debugger internal logging via CLI, the `--log-to` switch can be used:
```console
-m debugpy --log-to path/to/logs ...
```

When using the API, the same can be done with `debugpy.log_to()`:
```py
debugpy.log_to('path/to/logs')
debugpy.listen(...)
```

In both cases, the environment variable `DEBUGPY_LOG_DIR` can also be set to the same effect.

When logging is enabled, debugpy will create several log files with names matching `debugpy*.log` in the specified directory, corresponding to different components of the debugger. When subprocess debugging is enabled, separate logs are created for every subprocess.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e136560bf9b9bca5df18266cd19636a90427d0cf0d9721bfdbaed133b29b070d7e81073d8d0529ecda90038d90b0ee288)