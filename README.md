1. Initialize the remote repo with a `.gitignore` file

2. Clone to local:

    ```shell
    git clone <link to repository>
    ```

3. Create and activate virtual environment:

    ```shell
    # Linux
    # Create virtual environment
    python3 -m venv .venv --prompt web-app

    # Activate virtual environment
    source .venv/bin/activate
    ```

    ```shell
    # Windows/Powershell
    python -m venv .venv

    .venv\Scripts\activate
    ```

4. Install Django

    ```shell
    pip install Django
    ```

5. Create requirements file:

    ```shell
    pip freeze > requirements.txt
    ```

6. Create a django project:

    ```shell
    django-admin startproject config .
    ```