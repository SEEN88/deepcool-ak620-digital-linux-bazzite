# DeepCool AK Series Digital Air Cooler Monitor on Linux

This project enables monitoring of temperature and CPU utilization on DeepCool's AK series digital air cooler for Linux systems.  

## Dependencies

This script requires the following dependencies:
- Python 3
- `hidapi`
- `psutil`

You can install by running the provided `setup.sh` script:
```bash
usage: ./setup.sh <model> <sensor> [-dt | --disable-temp] [-du | --disable-utils]
        -dt, --disable-temp:    disable sensor temperature display
        -du, --disable-utils:   disable CPU utilization display
```

Available supported models:
- `ak620`
- `ak500s`

### Step-by-Step Guide

1. **Install Python Dependencies**: First, you need to install the necessary Python libraries, `hidapi` and `psutil`. These libraries allow the script to interact with the hardware and monitor system resources.

    Open a terminal and run the following commands:
    ```bash
    pip install hidapi
    pip install psutil
    ```
    Note: If you encounter permission errors, try adding --user to install the packages for your user only or use sudo to install them system-wide (not recommended for `pip`).

2. **Clone the Repository**: The script and necessary configuration files are hosted on GitHub. Use git to clone the repository to your local machine.
    ```bash
    git clone https://github.com/SEEN88/deepcool-ak620-digital-linux-bazzite
    ```

3. **Navigate to the Project Directory**: Change your current directory to the newly cloned project folder.
    ```bash
    cd deepcool-ak620-digital-linux-bazzite
    ```

4. **Look up the hardware temperature sensor**: Retrieve hardware temperature sensor label in the system. Run the following Python code snippet.
    ```python
    import psutil
    print(psutil.sensors_temperatures().keys())
    ```

5. **Run the Setup Script**: The `setup.sh` script will automate the configuration and setup process. Run the script by executing:

    Replace `model` with one of the available models matches your configuration and `sensor` with the label you retrieve from previous step.
    ```bash
    ./setup.sh <model> <sensor>
    ```

## Troubleshooting

1) If you encounter any errors related to HIDAPI or psutil, ensure that the dependencies are installed correctly by running the setup.sh script.
2) Make sure the AK620 digital air cooler is properly connected to your system and that the correct Vendor ID and Product ID are set in the script.
3) How to verify Product ID and Vendor ID ?  use lsusb -v to get the list of devices ans search for your cooler.

Credits
https://github.com/Algorithm0/deepcool-digital-info
