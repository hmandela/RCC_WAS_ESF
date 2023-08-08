# <span style="color:green"> Extended seasonal forecasts in agriculture and water resources sectors </span>
## 1- Download and install Anaconda
- For Windows, download the executable [here](https://repo.anaconda.com/archive/Anaconda3-2023.07-1-Windows-x86_64.exe)
- For Linux (Ubuntu), in the terminal run:
  ```bash
  sudo apt-get update
  sudo apt-get upgrade
  sudo apt-get install wget
  wget -c -r https://repo.anaconda.com/archive/Anaconda3-2023.07-1-Linux-x86_64.sh --no-check-certificate
  ```
  - Install anaconda
    ```bash
    bash https://repo.anaconda.com/archive/Anaconda3-2023.07-1-Linux-x86_64.sh
    ```
## 2- Create and activate the RCC_WAS_ESF environment

For Windows, run Anaconda prompt, and for Linux, launch the terminal. Copy and paste this code: 
  
  ```conda
  conda create -n RCC_WAS_ESF
  conda activate RCC_WAS_ESF
  ```
## 3- Create CDS API key

- Create an account with Copernicus by signing up [here](https://cds.climate.copernicus.eu/)
- Once you successfully create an account, kindly log in to your  Copernicus account [here](https://cds.climate.copernicus.eu/user) and note your `UID` and `API key`.

## 4- Configure .cdsapirc file
In your activated terminal, where the RCC_WAS_SF environment is active, kindly initiate the Python interpreter by entering the command `python3`. Subsequently, carefully copy and paste the below code, ensuring to replace "UID" and "API_KEY" with yours.
```python3
import os

config_data = '''url: https://cds.climate.copernicus.eu/api/v2
key: UID:API_KEY
verify: 0
'''

path_to_home = "/".join([os.path.expanduser('~'),".cdsapirc"])

if not os.path.exists(path_to_home):
    with open(path_to_home, 'w') as file:
        file.write(config_data)
```
Quit `python3` using  `ctrl+D`

## 5- Install the necessary packages for RCC_WAS_ESF

```bash
pip install xarray==2022.11.0 cdsapi 
pip install -c conda-forge cdsapi pandas jupyter
pip install -c r r-essentials r-irkernel
pip install -c conda-forge rasterio
pip install rioxarray
python -m ipykernel install --user --name=RCC_WAS_ESF
```


  

 
