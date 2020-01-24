# Installation on MacOs

### **Install in existing environment**

If you have an existing Python environment activated, you can install datasist with the command:

```text
$ pip install datasist
```

### **Install in a new virtual environment**

To install datasist ****in a virtual environment, you can use the Anaconda package.

{% hint style="info" %}
You must have  [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda Distribution](https://docs.anaconda.com/anaconda/) installed.
{% endhint %}

Confirm you have Anaconda installed:

```text
$ conda --version
```

Create new virtual environment and install Python 3.5 and above:

```
$ conda create -n yourenvname python=3.7 
```

Activate your environment:

```text
$ source activate yourenvname
```

Install datasist and other packages you need for your project

```text
$ pip install datasist
```

Test your installation: 

```text
$ python
Python 3.7.3 (default, Mar 27 2019, 16:54:48) 
[Clang 4.0.1 (tags/RELEASE_401/final)] :: Anaconda, Inc. on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import datasist as ds
>>> 
```


