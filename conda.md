# Conda Cheatsheet

---

## 1. Environment Management

- **Create env:**  
  ```bash
  conda create -n myenv python=3.8
  ```
- **Activate env:**  
  ```bash
  conda activate myenv
  ```
- **Deactivate env:**  
  ```bash
  conda deactivate
  ```
- **List envs:**  
  ```bash
  conda env list
  ```
- **Remove env:**  
  ```bash
  conda remove -n myenv --all
  ```

---

## 2. Package Management

- **Install package:**  
  ```bash
  conda install numpy
  ```
- **Install specific version:**  
  ```bash
  conda install pandas=1.2.0
  ```
- **Install from channel:**  
  ```bash
  conda install -c conda-forge opencv
  ```
- **Update package:**  
  ```bash
  conda update scipy
  ```
- **Remove package:**  
  ```bash
  conda remove matplotlib
  ```

---

## 3. Environment Export & Import

- **Export env:**  
  ```bash
  conda env export > environment.yml
  ```
- **Create from file:**  
  ```bash
  conda env create -f environment.yml
  ```

