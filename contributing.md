# Contributing to datasist

Thanks for considering contributing to Datasist!

All contributions, bug reports, bug fixes, documentation improvements, enhancements, and ideas are welcome here.

Have something in mind and not sure, chat with us ****~~**here**~~

For first time contributors, you can find/raise issues on our [GitHub “issues” page](https://github.com/risenW/datasist/issues). Once you’ve found an interesting issue, and have an improvement in mind, next thing is to set up your development environment.

## **Working with the code**

Now that you have an issue you want to fix, enhancement to add, or documentation to improve, you need to learn how to work with GitHub and the datasist code base.

### Version control, Git, and GitHub

The datasist code is hosted on GitHub. To contribute you will need to sign up for a free GitHub account. We use Git for version control to allow many people to work together on this project. If you're new to Git and GitHub, the Official[ GitHub pages ](https://help.github.com/en/github/getting-started-with-github)is a great learning resource.

### Forking the Datasist Repository

You will need your own fork to work on the code. Go to the datasist [project page](https://github.com/risenW/datasist) and hit the Fork button. After forking the repo, copy the link, you will use this later

### Create a development environment

It is advisable to create a development environment to test all code changes. This helps isolate datasist settings from your other environments.

You can create a new virtual environment with conda. First, make sure you have either [Anaconda](https://docs.anaconda.com/anaconda/) or [miniconda](https://docs.conda.io/en/latest/miniconda.html) installed.

Confirm you have Anaconda installed:

```text
conda --version
```

Create new virtual environment and install Python 3.5 and above:

```
$ conda create -n datasist-dev python=3.7 
```

Activate your environment:

- macOS and Linux:
```text
$ source activate datasist-dev
```

Windows:
```text
activate datasist-dev
```
Next, you will clone your forked repository to your local machine. Run the following command

```text
git clone https://github.com/your-user-name/datasist.git
```

This creates the directory **datasist** and connects your repository to the upstream \(main project\) repository.

Next, change directory to datasist, build and install:

```text
    cd datasist
    python setup.py build
    pip install -e .
```

Test that datasist was successfully installed by starting a Python REPL and import datasist

```python
$ python
Python 3.7.5 (default, Oct 25 2019, 15:51:11) 
[GCC 7.3.0] :: Anaconda, Inc. on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import datasist as ds
>>> 
```

If there is no error after importing datasist, you're ready to start contributing. Now you can fire up your favorite IDE and start implementing your changes.

However, if you will encounter a ModuleNotFound error while importing datasist package - just as captured below, you can take note of the package name, exit python interactive prompt and run pip install 'missing package' on your command line. You can thereafter proceed to import datasist after the missing package is successfully installed.
<p align="left">
  <img src="https://res.cloudinary.com/ibiz-ng/image/upload/v1594476943/mnfe_qxgusk.png" width="350" alt="ModuleNotFoundError">
</p>

## Docstrings Guidelines

Docstrings are an important part of coding and we encourage you to write clear and concise docstrings for your functions, methods and classes. Docstrings written for your code are automatically used to generate the datasist documentation.

 Our guidelines for writing docstrings are:

* Define what the function does. 
* Define all parameter types and what they do.
* State the return values.
* Use the correct spacing and indentation as this affects the documentation generated automatically.
* Add Example usage.

Below is a sample docstrings for a function that adds two Pandas DataFrame together:



```python
    def add_df(df1=None, df2=None):
        '''
        A function to add two dataframes together.  

        Parameters:
        ------------
        df1: DataFrame, Series
            The first dataframe to add.

        df1: DataFrame, Series
            The second dataframe to add.

        Returns:
        ---------
            DataFrame: Concatenation of the two dataframe
        
        Example:
        ---------
        >>> df1 = pd.DataFrame([1,2,3,4)
        >>> df2 = pd.DataFrame(['a','b','c','d')
        
        >>> add_df(df1,df2)

        '''

        #check if dataframe is None
        if df1 is None:
            raise ValueError('df1: Expected a DataFrame, got None')

        if df2 is None:
            raise ValueError('df1: Expected a DataFrame, got None')

        final_df = df1 + df2

        return final_df
```

## Writing tests

We strongly encourages contributors to write test for their code. Like many packages, datasist uses [**pytest**](https://docs.pytest.org/en/latest/)**.**

All tests should go into the tests sub-directory and placed in the corresponding script. The tests folder contains some current examples of tests, and we suggest looking to these for inspiration.

The easiest way to verify that your code is correct is to explicitly construct the result you expect \(expected\), then compare it to the actual result \(output\).

### Using pytest

Here we show an example of a test case we wrote for the **drop\_redundant** function in the **feature\_engineering** module. This test is placed in the **test\_feature\_engineering.py** file inside the **tests** folder. The function is shown first below.

```python
    def drop_redundant(data):
        '''
        Removes features with the same value in all cell. Drops feature If Nan is the second unique class as well.
    
        Parameters:
        -----------------------------
            data: DataFrame or named series.
    
        Returns:
    
            DataFrame or named series.
        '''
    
        if data is None:
            raise ValueError("data: Expecting a DataFrame/ numpy2d array, got 'None'")
    
        #get columns
        cols_2_drop = _nan_in_class(data)
        print("Dropped {}".format(cols_2_drop))
        df = data.drop(cols_2_drop, axis=1)
        return df
```

The corresponding test for the function above is:

```python
import pytest
from datasist import feature_engineering
import pandas as pd
import numpy as np

df = pd.DataFrame({'country': ['Nigeria', 'Ghana', 'USA', 'Germany'],
                    'size': [280, 20, 60, np.NaN],
                    'language': ['En', 'En', 'En', np.NaN]})


def test_drop_redundant():
    expected = ['country', 'size']
    output = list(feature_engineering.drop_redundant(df).columns)
    assert expected == output
```

### Running the test case

To run the test case, navigate the **tests/** subfolder and run the following command.

```text
pytest tests
```

Learn more about pytest [here](http://docs.pytest.org/en/latest/)

## Adding your changes to Datasist

### Committing your code

Once you’ve made changes, you can see them by typing:

```text
git status
```

Next, you can track your changes using

```text
git add .
```

Next, you commit changes using:

```text
git commit -m "Enter any commit message here"
```

### Pushing your changes

When you want your changes to appear publicly on your GitHub page, you can push to your forked repo with:

```text
git push
```

## Review your code and finally make the pull request

If everything looks good, you are ready to make a pull request. A pull request is how code from a local repository becomes available to the Datasist community and can be reviewed and eventually merged into the master version. To submit a pull request:

* Navigate to your updated repository of datasist on GitHub
* Click on the Pull Request button
* Write a description of your changes in the Preview Discussion tab
* Click Send Pull Request.

This request will be reviewed by datasist maintainers and if found to be OK, will be merged into the master branch.

#### **Hooray! You're now a contributor to datasist. Now go bask in the euphoria!**

