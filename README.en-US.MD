# Irisight

![Irisight Banner](assets/IrisghtBanner.png)

### Irisight is a project that aims to make the day-to-day life of visually impaired or blind people easier. To succeed in this goal, it uses a handful of different technological solutions to interpret and understand the surroundings of the wearer. It filters important information and guides the wearer through the environment with the help of the interpreted data. Irisight is part of the german engineering competition "Jugend Forscht".

## Information & Metadata

* This organization currently only acts as a central hub for saving code and important data for us. Soon we hope to have public repositories, showcasing some of our code, our development process and parts of the solutions itself.
* Irisight is a private project, due to being enlisted in the competition. Contributions are not possible at this time.
* You can find more information on this project [here](https://www.jugend-forscht.de/stiftung-jugend-forscht-e-v.html)

## Technical information
Irisight is divided into two parts, On-Device and Backend. On-Device is the part of Irisight, that runs locally on the users device and it's main task is interpreting and handling
all the data necessary to make sense of the environment and safely guide the wearer through it. It filters all important data and interacts with the user through sound. Part of the data is sent to the backend, which processes information and data that the local device couldn't. Such information might be the specific description of a scene to a precision which only Google Vision or some Cloud Vision provider can offer, or the fetching of weather data.

### On-Device

* The main part of this code is written in python and handles all tasks for the local device
* A local database ensures important logs and data is not lost and available without an internet connection
* A local offline-detection model ensures that data from the camera is interpreted swiftly and locally, without the need of an internet connection
* Irisight has some handy sensors on board, to pull relevant data even if it's offline.

### Backend

* The backend is broken down into many smaller processes, each one with its own task.
* The main-controller handles almost all requests and distributes tasks across the different processes. It also handles communication with the local device.
* The rest-controller handles asynchronous api request (i.e., fetching weather data) and forwards the information to the main controllers queue.
* The UWB-controller is a separate process, which handles all UWB data important to navigation in buildings. It communicates directly with the local device.
* All controllers write into separate database tables and log files to ensure no important data is being lost.

> [!NOTE]
> This scheme is bound to be evolved over the course of development. This is just a temporary blueprint.


## Questions or want to contact us?

Write us an email on `info-irisght@lucidev.me` or contact us via GitHub. More information on https://lucidev.me/projects