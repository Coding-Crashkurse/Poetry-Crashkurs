# Poetry Crashkurs

### Projekt initialisieren

Der Crashkurs ist auf PyCharm und Windows ausgerichtet, wird zunächst Fokus darauf gelegt, PyCharm so zu konfigurieren, dass man den korrekten Python Interpreter verwendet.
1. Settings -> Python Interpreter -> Add -> Pfad zu Interpreter setzen (Python 3.11), bei mir: `C:\Users\User\AppData\Local\Programs\Python\Python311`
2. Execution Policy auf "RemoteSigned" setzen: `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser`

Poetry sollte in die globale Environment installiert werden.
- Windows (PowerShell): `(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | py -`
- Linux, macOS, WSL: `curl -sSL https://install.python-poetry.org | python3 -`

Poetry zu PATH hinzufügen:

- $HOME/.local/bin on Unix.
- %APPDATA%\Python\Scripts on Windows.
- $POETRY_HOME/bin if $POETRY_HOME is set.

Version von Poetry überprüfen: `poetry --version`

Poetry config:
```
poetry config --list
poetry config virtualenvs.create false --local
export POETRY_VIRTUALENVS_PATH=/path/to/virtualenvs/directory
```


Poetry sollte in einer virtuellen Umgebung genutzt werden. Dafür gibt es in Poetry das Command `poetry shell`

Hilfreiche Commands für Envs:
```
poetry env info
poetry use xxx
poetry env info --path
poetry env list
poetry env remove xxx
```


Neues Projekt erstellen: `poetry new project`

Initialisierung in Projekt: `poetry init`


### Dependencies verwalten

Dependency hinzufügen: `poetry add pandas`

Dev-Dependency hinzufügen: `poetry add pytest --dev`

Packages updaten: `poetry add package@latest`


### Version constraints

Detaillierter Überblick hier: https://python-poetry.org/docs/dependency-specification/

Dependencies exportieren: `poetry export -f requirements.txt --output requirements.txt`


