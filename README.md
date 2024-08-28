1. Initialize the remote repo with a `.gitignore` file

3. Clone to local:

    ```shell
    git clone <link to repository>
    ```

4. Create and activate virtual environment:

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

    .\.venv\Scripts\activate
    ```

5. Install Django

    ```shell
    pip install Django
    ```

6. Create requirements file:

    ```shell
    pip freeze > requirements.txt
    ```

7. Create a django project:

    ```shell
    django-admin startproject config .
    ```

