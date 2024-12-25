<!--
*** Thanks for checking out this README Template. If you have a suggestion that would
*** make this better, please fork the tinyml-mapping-backlight and create a pull request or simply open
*** an issue with the tag "suggest".
*** Thanks again! Now go create something AMAZING! :D
***
***
***
*** To avoid retyping too much info. Do a search and replace for the following:
*** fullmakeralchemist, tinyml-mapping-backlight, twitter_handle
-->

<!--#     The TensorFlow Microcontroller Challenge    -->
   <h1>Needs Assessment Patient Perspective</h1>

   <h2>Primer acercamiento: Análisis de datos "Empoderando a los pacientes: Streamlining de recopilación de datos para satisfacer las necesidades y las satisfacciones de los pacientes"</h2>

<!-- PROJECT LOGO -->

<br />
<p align="center">

  <a href="https://github.com/fullmakeralchemist/">
    <img src="assests\Data analsys.png" alt="Logo" width="720">
  </a>
  -->
  <br />
  

  <img src="https://img.shields.io/github/languages/top/fullmakeralchemist/data_analysis_bootcamp?style=for-the-badge" alt="License" height="25">
  <img src="https://img.shields.io/github/repo-size/fullmakeralchemist/data_analysis_bootcamp?style=for-the-badge" alt="GitHub repo size" height="25">
  <img src="https://img.shields.io/github/last-commit/fullmakeralchemist/data_analysis_bootcamp?style=for-the-badge" alt="GitHub last commit" height="25">
  <img src="https://img.shields.io/github/license/fullmakeralchemist/data_analysis_bootcamp?style=for-the-badge" alt="License" height="25">
  <a href="https://www.linkedin.com/in/padrondata/">
    <img src="https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555" alt="LinkedIn" height="25">
  </a>
  <!--
  <a href="https://twitter.com/makeralchemist/">
    <img src="https://img.shields.io/twitter/follow/makeralchemist?label=Twitter&logo=twitter&style=for-the-badge" alt="Twitter" height="25">
  </a>
  -->
  
  <!-- <h3 align="center">Tiny ML in Mapping Dance, Visual Arts and interactive museums</h3>-->
  <p align="center">
    <h2>:warning: Hay que descargar los datos de Kaggle :warning:</h2>
    <h3>Demo de la app dashboard en Streamlit Share -------></h3>
    <br />
    <a href="https://subirs3.streamlit.app/"><strong>Proyecto Dashboard»</strong></a>
    <br />
  <br />
</p>
<br />

<!-- TABLE OF CONTENTS -->
## Table of Contents

* [About the Project](#about-the-project)
  * [Motivation](#motivation)
  * [Built With](#built-with)
* [Getting Started](#getting-started)
  * [Introduction](#introduction)
  * [Prerequisites](#prerequisites)
  * [Raspberry Pi 4 configuration to run the code](#raspberry-pi-4-configuration-to-run-the-code)
* [Creating a Streamlit WebApp for upload files from users](##creating-a-streamlit-webapp-for-upload-files-from-users)
  * [Setup in Windows](#setup-in-windows)
  * [Getting the MQTT library for the Arduino boards](#getting-the-mqtt-library-for-the-arduino-boards)
* [Methodology](#methodology)
  * [Arduino and Raspberry](#arduino-and-raspberry)
* [Database Design](#database-design)
  * [Key Entities](#key-entities)
  * [Relationships](#relationships)
  * [Key Entities](#key-entities)
* [Challenges I ran into and What I learned](#challenges-i-ran-into-and-what-i-learned)
* [Observations about the project](#observations-about-the-project)
* [Accomplishments that I'm proud of](#accomplishments-that-im-proud-of)
* [What's next for the project](#whats-next-for-weather-data-collection)
* [License](#license)
* [Contact](#contact)


<!-- ABOUT THE PROJECT -->
## About The Project

<!-- [![Tiny ML in Mapping Dance](https://i9.ytimg.com/vi/3YUVTDTo-Zk/mq1.jpg?sqp=CNTs2IcG&rs=AOn4CLBiPsvQ2bGNVZvn_j-nJXj8d81hLA)](https://www.youtube.com/watch?v=3YUVTDTo-Zk) -->

El objetivo de este proyecto es realizar un análisis en profundidad de las necesidades del paciente en los hospitales de EE. UU., centrándose en identificar áreas clave donde los pacientes pueden sentirse desatendidos o frustrados. A través de este análisis, mi objetivo es empoderar a los pacientes dándoles una voz en el proceso de atención médica y ayudándolos a resaltar problemas sistémicos que podrían afectar su experiencia de atención.

I didn't have enough time to add this documentation to the repo but here is the pdf version:

Run the following tutorial [following tutorial](https://github.com/fullmakeralchemist/dataengweather/blob/master/pdf/DE%20Documentacion%20flujo%20csv%20AWS.pdf) to start working with a workflow of data in AWS.

The code of the Lambda function can be found in [lambda.py](https://github.com/fullmakeralchemist/dataengweather/blob/master/lambda.py)

## Challenges I ran into and What I learned

One of the main challenges was finding how to send data from Arduino directly to AWS. As such, there is no documentation about it. Currently, the only option available is using one intermediary as it is Raspberry Pi to use it as a channel of obtaining the data automatically but it has a cost getting one and setting it.

The second main challenge was how many data variables can we read on an Arduino card since only few cards have the capacity to read specific sensors, these cards mostly do not have the necessary sensors to read the necessary pressure, humidity and temperature data. In addition, they only have Bluetooth communication, which makes communication with Streamlit difficult.

Finally, this is the first time I've used AWS API with Streamlit. In the end, I learned that whenever you may think that you found no way out, motivation can help you find alternative solutions with these resources.


## Observations about the project

Streamlit Share needs a special env variable for the credentials in AWS here is the link for documentation. Due to lack of time and knowledge of cloud tools that allow Streamlit Share to communicate with Arduino remotely using the communication protocol used, this project can only be used at the moment to communicate locally and send the data to S3 using Raspberry Pi also is really difficult and not recomendable using Windows to manage local brokers.

In addition, the Streamlit app has 1 path to save files for just one user. It is necessary to implement the route for different users to avoid putting data from different users to just one folder.

The data set is just for temperature, pressure and humidity is necessary to do implement more sensors to get more data also the time is set to register data each 20 seconds is necessary to do more research about the timing of records this can increase the size of the data, also for the moment i don’t have the calculation about how many data can be saved in the bucket and the cost so having data from multiple users and historical data.

## Accomplishments that I'm proud of

- Creation of a custom script to collect information and the option to include more variables.
- Building an ERD model with a first structure analyzing possible options for data.
- Apply knowledge of communication protocols with Data Engineering real time data collection.
- Create an app using Streamlit.
- Start creating a tool that will help others.

## What's next for Weather Data Collection

- Find more options to send data from Arduino to AWS
- Obtain more information and, if possible, include more variables and sensors.
- Add the option to do dashboarding with the collected data to the app.

## License


<!-- CONTACT -->
## Contact

Eduardo Padron - [LinkedIn: @padrondata](https://www.linkedin.com/in/padrondata/)