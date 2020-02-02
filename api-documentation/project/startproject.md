# startproject

## Description

Creates a standard data science project directory. This helps in easy team collaboration, rapid prototyping, easy reproducibility and fast iteration.The directory structure is by no means a globally recognized standard, but was inspired by the folder structure created by the Azure team \([https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/overview](https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/overview)\) 

![](../../.gitbook/assets/image%20%281%29.png)

#### Project Structure

**data**: Stores data used for the experiments, including raw and intermediate processed data.

* _processed_: stores all processed data files after cleaning, analysis, feature creation, etc.
* _raw_: Stores all raw data obtained from databases, file storages, etc.

**outputs**: Stores all output files from an experiment.

* _models_ : Stores trained binary model files. This are models saved after training and evaluation for later use.

**src**: Stores all source code including scripts and notebook experiments.

_scripts_ : Stores all code scripts usually in Python/R format. This is   usually refactored from the notebooks.

* _modeling_: Stores all scripts and code relating to model building, evaluation and saving.
* _preparation_: Stores all scripts used for data preparation and cleaning.
* _ingest_: Stores all scripts used for reading in data from different sources like databases, web or file storage.

_notebooks_ : Stores all Jupyter notebooks used for experimentation.

```python
def start_project(project_name=None)
    ''' 
    Parameters:
    --------------
        project_name: String, Filepath
        
            Name of filepath of the directory to initialize and create folders.
            
        Returns:
            None
    '''
```

## Examples

### Start project from terminal. 

If you have datasist installed, you can start a new project from the terminal as shown below:

```bash
>>> startproject my_new_shiny_project
Creating project my_new_shiny_project
Project created successfully in /home/johndoe/my_new_shiny_project
>>> cd my_new_shiny_project
config.txt  data  outputs  README.txt  src


```

### Start project with Editor

```python
>>> python
Python 3.7.5 (default, Oct 25 2019, 15:51:11) 
[GCC 7.3.0] :: Anaconda, Inc. on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import datasist as ds
>>> ds.project.startproject("new_project")
Creating project new_project
Project created successfully in /home/johndoe/new_project

```



To help us improve this documentation, visit the datasist-doc [repository](https://github.com/risenW/datasist-doc) 

