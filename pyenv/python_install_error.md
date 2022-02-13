# Pyenvでpythonがインストールできなくなった

## 現象

```
$ pyenv install 3.9.0
Downloading Python-3.9.0.tar.xz...
-> https://www.python.org/ftp/python/3.9.0/Python-3.9.0.tar.xz
Installing Python-3.9.0...
WARNING: The Python bz2 extension was not compiled. Missing the bzip2 lib?
ERROR: The Python ssl extension was not compiled. Missing the OpenSSL lib?

Please consult to the Wiki page to fix the problem.
https://github.com/pyenv/pyenv/wiki/Common-build-problems


BUILD FAILED (Ubuntu 20.04 using python-build 1.2.21-1-g943015eb)

Inspect or clean up the working tree at /tmp/python-build.20220211071033.237001
Results logged to /tmp/python-build.20220211071033.237001.log

Last 10 log lines:
fi
Looking in links: /tmp/tmpsbyx3j0q
Processing /tmp/tmpsbyx3j0q/setuptools-49.2.1-py3-none-any.whl
Processing /tmp/tmpsbyx3j0q/pip-20.2.3-py2.py3-none-any.whl
Installing collected packages: setuptools, pip
  WARNING: The script easy_install-3.9 is installed in '/home/ayumu/.pyenv/versions/3.9.0/bin' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
  WARNING: The scripts pip3 and pip3.9 are installed in '/home/ayumu/.pyenv/versions/3.9.0/bin' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
Successfully installed pip-20.2.3 setuptools-49.2.1
```

## 解決策

参考->[https://qiita.com/pokotsun/items/3ebab483b0e134ab1726](https://qiita.com/pokotsun/items/3ebab483b0e134ab1726)


```
$ CFLAGS=-I/usr/include/openssl LDFLAGS=-L/usr/lib pyenv install -v installしたいバージョン名,今回の場合は3.5.3
```

このあと再度`pyenv install x.x.x`すれば通った．