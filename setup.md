# Scalable GIS for Urbanists: Setup  
 
## Before the workshop

* **Windows users are strongly recommended to install Windows Subsystem for Linux 2 (WSL).** For instructions, see Windows section below.  
* Participants should have Python 3 and SSH. In order to verify whether these are installed and/or to install them on MacOS, Linux, or Windows, see the Appendix section below.   
* Python Packages: Fabric and Decorator. In a terminal window, type: 
    ```shell
    pip install fabric decorator
    ```
  (Participants familiar with `conda` or `venv`, can create an environment with the following dependencies: `python=3.10`, `fabric`, `decorator`) 
* Download and extract the following zip archive: [link](https://github.com/RS-DAT/JupyterDaskOnSLURM/archive/refs/heads/workshops.zip)
* Test the setup: 
    * Access the extracted folder in your terminal  (you might have to modify the path below): 
      ```shell
      cd ~/Downloads/JupyterDaskOnSLURM-workshops
      ```
    * Running:
      ```shell
      python runJupyterDaskOnSLURM.py
      ``` 
      should return: 
      ```shell
      usage: runJupyterDaskOnSLURM.py [-h] [--local_port LOCAL_PORT] [--wait_time WAIT_TIME] (--add_platform | --one_off | --uid UID) [--mode MODE]
      runJupyterDaskOnSLURM.py: error: one of the arguments --add_platform/-a --one_off/-oo --uid/-u is required 
      ``` 

## On the day of the workshop

* Download the SSH key for Spider using the link on the printout.
* Access the `JupyterDaskOnSLURM-workshops` folder in your terminal  (you might have to modify the path below): 
  ```shell
  cd ~/Downloads/JupyterDaskOnSLURM-workshops
  ```
* Edit the configuration file `config/platforms/platforms.ini` with your account information:
    * You can use `nano` (e.g. `nano config/platforms/platforms.ini` to start editing, Ctrl+X to quit); 
    * Replace the user name `stursdat-XX` with your user ID (e.g. `stursdat-01`);
    * Replace the SSH key path `/path/to/the/ssh-key/rsa_stursdat_XX` to the actual file path (e.g. `/Users/fnattino/Downloads/rsa_stursdat_01`).   
* Start a Jupyter session on Spider by running the following command:
  ```
  python runJupyterDaskOnSLURM.py --uid spider-stursdat --mode run
  ```
  Jupyter Lab should open up in your browser! 
  
  
## Appendix: System specific instructions

### MacOS: 
* To install any of the tools below, you can use Homebrew or an alternative package manager. 
    * To install brew: /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" 
* Python  
    * You can test whether Python is installed by opening Terminal and by typing:
      ```shell
      python3 --version
      ```
      which should output ‘Python 3.X.Y’ 
    * If above fails, install Python 3 (we recommend python 3.10):  
      ```shell
      brew install python@3.10
      ```
3. SSH 
    * You can test whether SSH is installed by opening Terminal and by typing: 
      ```shell
      ssh
      ```
      which should output a list of usage options. 
    * If above fails, install SSH:  
      ```shell
      brew install openssh
      ```
 
### Linux: 
* Python  
    * You can test whether Python is installed by opening Terminal and by typing:
      ```shell
      python3 --version
      ```
      which should output ‘Python 3.X.Y’ 
    * If above fails, install Python 3 (we recommend python 3.10) using the distribution package manager. For Ubuntu:  
      ```shell
      sudo apt-get install python3.10
      ```
3. SSH 
    * You can test whether SSH is installed by opening Terminal and by typing: 
      ```shell
      ssh
      ```
      which should output a list of usage options. 
    * If above fails, install SSH using the distribution package manager. For Ubuntu:  
      ```shell
      sudo apt install openssh-server
      ```
 
### Windows: 
1. Windows subsystem for linux 2 (WSL); To install WSL: 
    * Open PowerShell as administrator
    * Run `wsl --install` (by default the Ubuntu distribution will be installed) 
    * Restart PC 
    * After restarting, follow the instructions on the automatically opened Ubuntu terminal to setup ubuntu ID and password 
    * From now on, follow the above instructions as given for Linux, using the Ubuntu terminal to type in commands.  
