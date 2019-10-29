# Work method

## Computer and workstation
A good work habits is to have your code at only one place. Since a Mac cannot run any CUDA-enabled code, it's not a
good platform to chose to run and debug your deep learning code since it will likely use GPU acceleration and NVIDIA's
APEX library. But, macOS stays one of the best desktop environment for programming and working, making it an excellent
developer platform along with Linux.

If you want to work on macOS, your code should be only on your Mac and synchronized automatically with your desired 
deployment server or your personal Lab workstation. With PyCharm, this is very easy to achieve. This way, you will
never be out of sync and your code will never be overridden by obsolete versions of your code. Follow the [JetBrains
initial configuration steps](../apps/index.md#jetbrains) to get started.

This method is also a good way to get a couple of hundreds of Megabytes of more of VRAM on your personal workstation. By
using your personal laptop as desktop environment, you can disable the GNOME desktop environment which free up video 
resources on the GPU. Sometimes, it's all what it takes to fit your model into the limited 8 GB of VRAM we have on the
lab's GPUs.

Unfortunately, as a drawback, you'll likely have to get a dock for connecting two monitors and peripherals on your 
computer. Also, ensure your computer can run multiple external displays. For instance, a MacBook Air cannot have more 
than one external monitor, while MacBook Pro can have a maximum of two external monitors, making a three-display 
setup possible. See your computer manufacturer specifications. 


## Virtualenv
[Virtualenv](https://virtualenv.pypa.io/en/latest/) is a tool that lets you create an isolated Python environment for
your project. It creates an environment that has its own installation directories, that doesn’t share dependencies 
with other `virtualenv` environments (and optionally doesn’t access the globally installed dependencies either). 
You can even configure what version of Python you want to use for each individual environment. It's very much 
recommended to use `virtualenv` when dealing with Python applications.

### Installation

To install `virtualenv`, run
```
pip install virtualenv
```

### Usage

If you have a project in a directory called my-project you can set up virtualenv for that project by running:

```
$ cd my-project/
$ virtualenv venv
```

If you want your virtualenv to also inherit globally installed packages run:

```
$ virtualenv venv --system-site-packages
```

These commands create a `venv/` directory in your project where all dependencies are installed. You need to activate it 
first (in every terminal instance where you are working on your project):

```
$ source venv/bin/activate
```

You should see a `(venv)` appear at the beginning of your terminal prompt indicating that you are working inside the 
`virtualenv`. Now when you install something like this:

```
$ pip install <package>
```

It will get installed in the `venv/` folder, and not conflict with other projects.

To deactivate the virtual environment run:

```
$ deactivate
```

Important: Remember to add `venv` to your project's `.gitignore` file so you don't include this directory in your source 
code.


## Git

Every source code repository should include a README.md file describing how to contribute and work with your repository.

We usually define these sections : 

- Contributing
- Branch naming
- Commit syntax

Since we are aiming to standardize the way we work in the lab, below is a code sample your project should have.

```
## Contributing
If you find a bug or have an idea for an improvement, please first have a look at our [contribution guideline](https://github.com/sami-ets/SAMITorch/blob/master/CONTRIBUTING.md). Then,
- [X] Create a branch by feature and/or bug fix
- [X] Get the code
- [X] Commit and push
- [X] Create a pull request

## Branch naming

| Instance        | Branch                                              | Description, Instructions, Notes                   |
|-----------------|-----------------------------------------------------|----------------------------------------------------|
| Stable          | stable                                              | Accepts merges from Development and Hotfixes       |
| Development     | dev/ [Short description] [Issue number]             | Accepts merges from Features / Issues and Hotfixes |
| Features/Issues | feature/ [Short feature description] [Issue number] | Always branch off HEAD or dev/                     |
| Hotfix          | fix/ [Short feature description] [Issue number]     | Always branch off Stable                           |

## Commits syntax

##### Adding code:
> \+ Added [Short Description] [Issue Number]

##### Deleting code:
> \- Deleted [Short Description] [Issue Number]

##### Modifying code:
> \* Changed [Short Description] [Issue Number]

##### Merging branches:
> Y Merged [Short Description]

```


## Containers

We observed that many research projects now ship with a `Dockerfile` or Singularity build file for automatically 
building the required libraries and run your experiments inside a container. This is a way to make experiments 
reproducible between researchers and to accelerate research. Your project, in its final stage, should have these files, 
especially if your code is used in for a publication.


## Clean code and tests

SAMI Lab has two libraries in active development in which we emphasize on clean coding, good practices, and tests. This 
is something we would like to transpose in everyone's code. 

While the libs kind of force you to write clean code, we know things can go wrong. 

If you are having trouble with your personal code, start writing unit tests in order to test key components of your
algorithm/code/input pipeline. It's very likely that if you are asking for questions, you will be answered by 
"Where are your tests?". Be prepared !
