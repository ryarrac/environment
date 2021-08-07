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

---
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

#### Deleting an environment

Use

```py
rmdir project_env \s
```
\s is used to delete the directories as well.

Alternatively, you can also choose to **drag to recycle bin** to delete an environment.

---

#### Installing packages

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

This will give all the package names and versions of your environments. You can copy the outputs and create a **packages.txt** file 


---
## Best practices

It is better to create all virtual environments under one particular location. For instance, let us create a folder projects and then put everything inside that folder.

```py
mkdir projects
python -m venv  projects\venv
```
This will create venv environment inside folder projects.

Now activate the environment. 

```py
projects\my_venv1\Scripts\activate.bat
```
We had created a packages.txt file. Now, with the help of the file, we can recreate the environemt.

```py
pip install -r \path\to\the\file\packages.txt
```

<h3><span style="color:#f5730a">Never Never!!!</span></h3>

Usual structure of the project is like the following.
<pre>
PROJECTS
└───venv
    ├───Include
    ├───Lib
</pre>

<span style="color:#f5730a">Never ever put any of your scripts inside the **venv** folder. Because you can delete and create the **venv**, whenever you like to. Therefore, none of your files should be created in this directory. Always put your files under **PROJECTS** folder and backup those, whenever necessary.
</span>



### Virtual environment with access to system packages

Usually the packages install in the global (system) environment is not available under the virtual environment. If you want to make all the packages of your global environment be available under your virtual environments, then instead of `python -m venv` command, use the following command: 

```py
python -m venv projects\venv --systemn-site-packages
```

All the global packages will be available now, inside the virual environment. However, that doesn't limit you from installing packages from installing packages in your virtaul environment. A `pip install <package name>` from your activated environemnt will install packages only inside your virtual environment. 

If you try listing installed packages, with `pip list` it will show you all the packages installed in your global environment and virtual environment. Sonmetimes, you may want to see only the list of packages installed in your virtual environemnt. Use the following command to list only those packages installed in your virtual environment.

```py
pip list --local
```

If you want to create a **packages.txt** file containing only local packages, then

```py
pip freeze --local
```
