# Setting up your environment and sourcing the data

## Objective

Set up your Python environment, test Zipline, and download the Quandl Wiki data  

## Workflow

1. Install [Docker Desktop](https://docs.docker.com/desktop/) for [Windows](https://docs.docker.com/docker-for-windows/install/) or [Mac OS](https://docs.docker.com/docker-for-mac/install/).
    - Review Getting Started guides for [Windows](https://docs.docker.com/docker-for-windows/) or [Mac OS](https://docs.docker.com/docker-for-mac/). Under Preferences, look for Resources to find out how you can increase the memory allocated to the container; the default setting is too low given the size of the data. Increase to at least 4GB.
2. Clone the starter repo using the following command: `git clone ` and change into the new directory.
3. [Register](https://www.quandl.com/sign-up) for a (free) personal Quandl account to obtain an API key that you'll need in the next step.  
3. We'll be using an image based on the Ubuntu 20.04 OS with the Anaconda Python distribution installed. It also contains two conda environments, one to run Zipline and one for everything else. The following command does several things at once:
    ```docker
    docker run -it -v $(pwd):/home/manning -e QUANDL_API_KEY=<yourkey> --name liveproject appliedai/manning:starter bash
    ```
    - it pulls the image from the Docker Hub account `appliedai` and the repository `manning` with the tag `starter`
    - creates a local container with the name `liveproject` and runs it in interactive mode,
    - mounts the current directory containing the starter project files as a volume in the directory `/home/manning` inside the container,
    - sets the environment variable `QUANDL_API_KEY` with the value of your key (that you need to fill in for `<yourkey>`), and
    - starts a `bash` terminal inside the container, resulting in a new command prompt.
4. Now you are running a shell inside the container and can access the `conda environments`.
    - Run `conda env list` to see that there are a `base`, `ml4t` (default), and a `ml4t-`zipline` environment.
    - You can switch to another environment using `conda activate <env_name>`. 
        - However, before doing so the first time, you may get an error message suggesting you run `conda init bash`. After doing so, reload the shell with the command `source .bashrc`. 
5. To run Zipline backtests, we need to `ingest` data. See the [Beginner Tutorial](https://www.zipline.io/beginner-tutorial.html) for more information. The image has been configured to store the data in a `.zipline` directory in the directory wehre you started the container (which should be the root folder of the project starter code). 
    - From the command prompt of the container shell, run
    ```bash
    conda activate ml4t-zipline
    zipline ingest
    ``` 
   - You should see numerous messages as Zipline processes around 3,000 stock price series
5. Now we would like to test Zipline and the [juypter](https://jupyter.org/) setup. You can run notebooks using either the traditional or the more recent Jupyter Lab interface; both are available in all `conda` environments. Moreover, you start jupyter from the `base` environment and switch the environment from the notebook due to the `nb_conda_kernels` package (see [docs](https://github.com/Anaconda-Platform/nb_conda_kernels)). To get started, run one of the following two commands:
    ```bash
    jupyter notebook --ip 0.0.0.0 --port 8888 --no-browser --allow-root
    jupyter lab --ip 0.0.0.0 --port 8888 --no-browser --allow-root
   ```
    - The terminal will display a few messages and at the end indicate what to paste into your browser to access the jupyter server from the current working directory.
6. To test Zipline, run the ```zipline_test.ipynb``` notebook. It contains the example from the Zipline tutorial referenced in step 5 and should display the backtest results at the end.
7. Now, after logging into Quandl, download the [Quandl Wiki Stock data](https://www.quandl.com/tables/WIKIP/WIKI-PRICES/export) and unzip into the root directory of the project starter files as `us_stocks.csv`.
8. Now, simplify the data as follows (see pandas [docs](https://pandas.pydata.org/docs/) as necessary): 
    - Convert the `date` column to `datetime` format
    - Select stock price data only from 2000 onwards
    - Set `ticker` and `date` as index
    - Keep only the adjusted open, low, high, close, and volume (OHLCV) prices, and rename by removing the `adj_` prefix
    - Store in HDF5 format for fast access.  
   
## Importance to project
- We need our programming environment up and running to proceed with our project; Docker helps us avoid some trickier and OS-dependent installation issues.
- It's good to know that things work, so we run a quick test that avoids running into problems later.
- Finally, we need data to build an ML model and a trading strategy. Now we have consistent data that we can use in the notebook to engineer features and design a predictive model, as well as run a Zipline backtest on.

## Resources

- [Docker - Getting Started Guide](https://docs.docker.com/get-started/)
- [Docker Cheatsheet](https://raw.githubusercontent.com/sangam14/dockercheatsheets/master/dockercheatsheet8.png)
- [A comprehensive introduction to Docker, Virtual Machines, and Containers](https://www.freecodecamp.org/news/comprehensive-introductory-guide-to-docker-vms-and-containers-4e42a13ee103/)