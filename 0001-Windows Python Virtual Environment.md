# Virtual Environment in Python (Windows)
    
Unlike virtualenv or pipvenv, venv comes bundled with python standard library. We need nothing extra to use this. 
Lets do a pip list to cnheck default packages.

```py
pip list
```
Go to the folder in which you want to create your virual environment (e.g Desktop or Downloads)

```sh
cd Downloads
```

Now, create the virtual environment

```sh
python -m venv  project_env
```
This will create an python environment with the name **project_env**.

#### Activate the environment

```sh
project_env\Scripts\activate.bat
```

If the environment is activated, it will be reflected in your promt. The first phrase of your prompt will be the new environment name.

```sh
(project_env)C:\user\ryarrac\Downloads>
```

#### Deactivate the environment

Just use the command

```py
deactivate
```


Inside this environment, if we run 
```py
pip list
```
it will show only show two packages. If we install any other packages here, it will be available only for this environment. 

#### Installing other required packages

Install **Numpy** in this environment

```py
pip install numpy
```

#### Export an environment

Say, we need to create an identical environment like our current environment, then we can export our environment with 

```py
pip freeze
```

This will give all the package names and versions of your environments. You can copy the outputs and create a **requirement.txt** file 