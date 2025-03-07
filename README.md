# Working With Tox
Tox is a tool used for **automating testing in Python** across multiple environments. It helps ensure that your code runs correctly on different Python versions and dependency sets. 

---

### **1. Installing Tox**
```sh
pip install tox
```

---

### **2. Setting Up a `tox.ini` Configuration File**
Create a `tox.ini` file in your project root directory.

```ini
[tox]
envlist = py38, py39, py310

[testenv]
deps =
    pytest
commands =
    pytest
```

#### Explanation:
- `envlist = py38, py39, py310` → Defines the Python versions to test (e.g., Python 3.8, 3.9, 3.10).
- `[testenv]` → Defines the environment setup.
- `deps = pytest` → Installs dependencies (`pytest` in this case).
- `commands = pytest` → Runs tests using `pytest`.

---

### **3. Running Tox**
Run Tox in the project directory:
```sh
tox
```
Tox will create isolated virtual environments and execute tests in each.

---

### **4. Specifying a Python Version**
If you want to test only a specific environment:
```sh
tox -e py39
```

---

### **5. Using Tox for Linting**
You can also use Tox to run tools like `flake8` for linting.

```ini
[testenv:lint]
deps = flake8
commands = flake8 src/
```
Run it with:
```sh
tox -e lint
```

---

### **6. Specifying Dependencies in `requirements.txt`**
Instead of listing dependencies in `tox.ini`, you can specify:
```ini
[testenv]
deps = -r requirements.txt
```

---