# How to set up working environment for deep learning

## Background

This document explains how to set up a virtual environment for tensorflow & keras on GPU server running ubuntu 16.04.

## Prerequisite

You need to install the most updated cuda and cuDNN libraries. Refer the following document for the detailed instructions.

- [Installing TensorFlow on Ubuntu  |  TensorFlow](https://www.tensorflow.org/install/install_linux#InstallingVirtualenv)

**Note**: The required libraries are already installed on the GPU server, and you don't have to worry about this step.

## Python virtual environments

You may need to have different versions/sets of python interpreter and packages for different projects. In such a case, you may build virtual environments (defined as the below) for each project.


[A virtual environment](https://docs.python.org/3/glossary.html#term-virtual-environment): A cooperatively isolated runtime environment that allows Python users and applications to install and upgrade Python distribution packages without interfering with the behaviour of other Python applications running on the same system.

You may refer the following documents for the details of virtual environments.
- [12. Virtual Environments and Packages — Python 3.6.5 documentation](https://docs.python.org/3/tutorial/venv.html)
- [Pipenv & Virtual Environments — The Hitchhiker's Guide to Python](http://docs.python-guide.org/en/latest/dev/virtualenvs/)
- [Python Virtual Environments – A Primer – Real Python](https://realpython.com/python-virtual-environments-a-primer/)

## Virtual environment set up for tensorflow and keras

You can make a virtual environment `tf` for python3 as follows. You may put any name in the place of `tf` if you want to name your virtual environment differently. It is a common practice to put your virtual environment in ~/venv directory.

**Note**: `~` means your home directory. `~/venv/` means the directory `venv` under your home directory.

```bash
$ mkdir ~/venv/
$ cd ~/venv/
$ python3 -m venv tf
$ cd
```

To activate virtual environment, you need to execute the following command. The `(tf)` in the prompt indicates the virtual environment you are using.

```bash
$ source ~/venv/tf/bin/activate
(tf) $
```

To deactivate your virtual environment, you can use `deactivate` command as follows.
```bash
(tf) $ deactivate
$
```

Now you may install the necessary packages with [pip](https://packaging.python.org/tutorials/installing-packages/).

```bash
$ source ~/venv/tf/bin/activate
(tf) $ pip install --upgrade pip
(tf) $ pip install --upgrade tensorflow-gpu
(tf) $ pip install keras
(tf) $ pip install jupyter
(tf) $ pip install pandas
(tf) $ pip install seaborn
```

Now you can check if the required packages are properly installed.

```bash
(tf) $ python
Python 3.5.2 (default, Nov 23 2017, 16:37:01)
[GCC 5.4.0 20160609] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import keras
/home/chomg/venv/tf/lib/python3.5/site-packages/h5py/__init__.py:36: FutureWarning: Conversion of the second argument of issubdtype from `float` to `np.floating` is deprecated. In future, it will be treated as `np.float64 == np.dtype(float).type`.
  from ._conv import register_converters as _register_converters
Using TensorFlow backend.
>>>
```
