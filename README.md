# jupyter-quickstart

[![CI](https://github.com/LionelB5/jupyter-quickstart/actions/workflows/app.yml/badge.svg)](https://github.com/LionelB5/jupyter-quickstart/actions/workflows/app.yml)

Project containing a handful of Jupyter Notebooks that make use of libraries often used in the
field of data science.

Manually tested against Python 3.9.1

# Local environment setup

1. Navigate to the root of the project, and create a virtual environment:

    ```bash
    python -m venv venv
    ```

2. Once the virtual environment is created, activate it:

    **Linux**

    ```bash
    source venv/bin/activate
    ```

    **Windows**

    ```powershell
    .\venv\Scripts\activate.bat
    ```

3. Install the necessary dependencies from the `requirements.txt` file:

    ```
    pip install -r requirements.txt
    ```

4. Install the pre-commit hooks (optional but recommended)

    ```
    pre-commit install
    ```

# Running the notebooks

From within your activated virtual environment, run:

```bash
python -m jupyter notebook
```

# Formatting the code within the notebooks

This project uses [black](https://github.com/psf/black) for consistent code formatting.

To format the notebooks execute:

```bash
black .
```

Black is also executed as part of the pre-commit hooks.

# Installing new dependencies

This project uses `pip-compile` to [manage dependencies](https://youtu.be/LAig6s9Hkj0).

Before adding new dependencies, [ensure you have `pip-tools` installed](https://pypi.org/project/pip-tools/) (this package provides the `pip-compile` command).

To add a new dependency:

-   Add the package name of the new dependency to the `requirements.in` file.
-   Run the following command to pin the dependency and its transitive dependencies in the `requirements.txt` file.

    ```bash
    pip-compile requirements.in
    ```

-   Once the `requirements.txt` file has been regenerated, in an activated virtual environment, run:

    ```bash
    pip install -r requirements.txt
    ```
