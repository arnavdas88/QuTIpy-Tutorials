---
description: >-
  Installing the QuTIpy package directly from the official git repository (from
  source).
---

# Install with git

If you’d like to be able to update your QuTIpy code occasionally with the latest bug fixes and improvements, follow these instructions:

### Manual Installation

1. Make sure that you have [Git](https://git-scm.com/) installed and that you can run its commands from a shell. (Enter `git help` at a shell prompt to test this.)\

2.  Check out QuTIpy’s main development branch like so:

    ```
    $ git clone https://github.com/sumeetkhatri/QuTIpy.git
    ```

    _This will create a directory `QuTIpy` in your current directory._\

3. Make sure that the Python interpreter can load QuTIpy’s code. The most convenient way to do this is to use a virtual environment and [pip](https://pip.pypa.io/). The [contributing tutorial](https://docs.djangoproject.com/en/4.0/intro/contributing/) walks through how to create a virtual environment.\

4.  After setting up and activating the virtual environment, run the following command:

    ```
    $ python -m pip install -e QuTIpy/
    ```

    _This will make QuTIpy’s code importable. In other words, you’re all set!_



### PIP Installation

1. Install the package directly from [GitHub](https://github.com/sumeetkhatri/QuTIpy) using pip, like so:

```bash
$ python -m pip install https://github.com/sumeetkhatri/QuTIpy.git
```





{% hint style="info" %}
#### Check if the installation is successfull :&#x20;



Run the shell command ,

`$ echo "import qutipy; print(qutipy.version);" | python`&#x20;



This should output the version of qutipy installed in your system like this ,

`$ 0.1.0`
{% endhint %}



When you want to update your copy of the QuTIpy source code, run the command `git pull` from within the `QuTIpy` directory. When you do this, Git will download any changes.
