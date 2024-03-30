# BusShuttleDocker

This repository is a docker compose for replicating the local development environment.

### Install Prerequisites

* Download and install Docker Desktop (v2.3.0.3 is tested)
  * <a href="https://www.docker.com/products/docker-desktop" target="_blank">https://www.docker.com/products/docker-desktop</a>
  * You can follow the instructions if you are stuck at some point.
    * Windows: [https://docs.docker.com/docker-for-windows/install/](https://docs.docker.com/docker-for-windows/install/)
    * Mac: [https://docs.docker.com/docker-for-mac/install/](https://docs.docker.com/docker-for-mac/install/)
* Run the Docker executable and start when installing is done.

### Clone Repos

* Clone this repository first via the command below:
  * `git clone https://github.com/hergin/BusShuttleDocker.git`
* Then, cd into the folder and clone the other repositories:
  * **If you will contribute, fork these repositories first and clone your copies.**
    *  <a href="https://github.com/hergin/BusShuttleManagerDashboard.git" target="_blank">https://github.com/hergin/BusShuttleManagerDashboard.git</a>
    *  <a href="https://github.com/hergin/BusShuttleAPI.git" target="_blank">https://github.com/hergin/BusShuttleAPI.git</a>
    *  <a href="https://github.com/hergin/BusShuttleDriverApp.git" target="_blank">https://github.com/hergin/BusShuttleDriverApp.git</a>
  * You can do it via command line (or choose your own way of cloning a repository, NOT DOWNLOADING).  

    *  (Windows) **Shift+Right-click** to an empty place on that folder to open a command line.
    *   Run these commands (it assumes you have **git** installed and **git** command accessible in PATH environment variable):
        *   `git clone https://github.com/hergin/BusShuttleManagerDashboard.git`
        *   `git clone https://github.com/hergin/BusShuttleAPI.git`
        *   `git clone https://github.com/hergin/BusShuttleDriverApp.git`
  
### Run

* Run the following docker-compose command in the root folder (where docker-compose.yml is):
  * `docker-compose up`
  * This might take some time for the initial build.
  * If Docker prompts to share folder(s), confirm them.
* If you want to rebuild from scratch, try using --nocache option.
  * `docker-compose build --no-cache`
  * This might help if DB or any other initial setup has changed.
* If you have changed a port in docker-compose file, this might affect some URLs in the source code, such as API_URL. In this case, you should update some URLs manually in the source code.
  * In the BusShuttleManagerDashboard, BASE_API_URL, check this: <a href="https://github.com/hergin/BusShuttleMainRepository/blob/master/Manuals/NewDevelopmentManual.md#updating-paths-and-variables-for-local" target="_blank">https://github.com/hergin/BusShuttleMainRepository/blob/master/Manuals/NewDevelopmentManual.md#updating-paths-and-variables-for-local</a>
  * In the BusShuttleDriverApp, BASE_API_URL, check this: <a href="https://github.com/hergin/BusShuttleMainRepository/blob/master/Manuals/NewDevelopmentManual.md#run-the-app" target="_blank">https://github.com/hergin/BusShuttleMainRepository/blob/master/Manuals/NewDevelopmentManual.md#run-the-app</a>

### Browse

* Go to manager dashboard (<a href="http://localhost/BusShuttleManagerDashboard" target="_blank">http://localhost/BusShuttleManagerDashboard</a>), login (Sample user name : `local`, its password: `local`) and add:
  * A new driver in the Drivers page
  * A new bus in the Buses page
  * A new loop in the Loops page
  * A new stop in the Stops page
  * A new inspection item in the Inspection Items page
  * Assign the newly created stop to the newly created loop in Routes page
* Go to driver app (<a href="http://localhost:4201" target="_blank">http://localhost:4201</a>) and login (Sample user name : `shuttle`, its password: `bus`) and select these new driver, bus and loop.
  * Add some mileage information and check the inspection item.
  * Add some boarded and left behind.
  * Click Submit
  * Click Sign Off and Do Post Inspection
  * Check the inspection item and add some mileage information.
  * Click Finish
* Go to manager dashboard entries page (<a href="http://localhost/BusShuttleManagerDashboard/Pages/Entries.php" target="_blank">http://localhost/BusShuttleManagerDashboard/Pages/Entries.php</a>).
  * Select today and select the newly created loop.
  * If you see the entry you have created in this page, everything seems to be properly working.
