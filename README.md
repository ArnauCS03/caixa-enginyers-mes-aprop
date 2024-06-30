# UAB The Hack 👾 - Caixa Enginyers Challenge 🚐 💰
![hack](https://github.com/EncryptEx/caixa-enginyers-mes-aprop/assets/95536223/660c4c7d-4be9-4f1e-b416-04ecb7db1cb4)<br>

![caixa](https://github.com/EncryptEx/caixa-enginyers-mes-aprop/assets/95536223/10f07df9-2823-4616-bc31-0749219a8d9d)<br><br>

Our team has participated in the Hackathon hosted by Universitat Autònoma de Barcelona, where we implemented a solution for the project presented by Caixa Enginyers.<br>
Grup Caixa Enginyers is a cooperative credit and financial services entity, offering a wide range of banking, financial, and insurance solutions. <br><br>
## The challenge 
Design a software capable of proposing optimized routes for a mobile office (van) which visits a set of municipalities. Everything satisfying some restrictions, like the working day, going to some places on certain days of the month, and having only 4 vans. The routs had to obey some requirements for the contest organized by the Generalitat de Catalunya, which can be found [here](https://contractaciopublica.cat/ca/detall-publicacio/6d5220fb-70f6-42c7-bf85-b78ef0184427/300013925).<br><br>


## Authors  <img src="https://github.com/EncryptEx/caixa-enginyers-mes-aprop/assets/95536223/a16f7883-aabd-4d1e-8d33-ffcc8abad5a8" alt="logo" width="40"/>
- Arnau Claramunt
- Jaume López
- Pay Mayench

[![GitHub followers](https://img.shields.io/github/followers/ArnauCS03?label=ArnauCS03)](https://github.com/ArnauCS03) &nbsp;&nbsp; [![GitHub followers](https://img.shields.io/github/followers/EncryptEx?label=EncryptEx)](https://github.com/EncryptEx) &nbsp;&nbsp; [![GitHub followers](https://img.shields.io/github/followers/PauMayench?label=PauMayench)](https://github.com/PauMayench) <br><br>

---
<br>

>[!NOTE]  
> ### Project Technologies and Tools
> Here is the summary of the technologies and tools utilized in our project:
> - **Python**: Leveraged for the backend development.
> - **Laravel (php)**: Main framework for the web application development.
> - **Tailwind (CSS)**: Used for efficient and flexible styling in the web.
> - **Flask**: For building the APIs.
> - **Pandas**: Employed for data manipulation and analysis, and working with .csv files.
> - **OpenStreetMap**: Integrated for rich mapping functionalities.
> - **Leaflet**: Employed for the interactive map in our web.
> - **ngrok**: Utilized for secure tunneling to connect IPs.

<br><br>
# Table of Contents

1. [Project Overview](#project-ov)
2. [Challenges we ran into](#callenge)
3. [Project Setup](#project-setup)
4. [Learning](#learning)
5. [Next](#next)
6. [Screenshots](#screen)
7. [Licence](#license)<br><br>

<a name="project-ov"></a>
## Project Overview
We devided the work in forntend and backend. For the forntend we build a web with Laravel (php). And backend with Python and Flask, modeling the Algorithm. 

<a name="callenge"></a>
## Challenges we ran into
Finding a good modelizations and algorithm. Also the heuristic for calculating the optimal routes. Work with new frameworks, and moreover having to calculate distances from all pairs of cities. And little details like correcting the names of the dataset of small cities so the API recognised them inside Spain.

<a name="project-setup"></a>
## Project Setup
First of all, we need to run the solver in order to compile its results into a readable json file:

To do that, we'll need to create a virtualenviroment and install all the requirements
```
cd ./solver
```
```
virtualenv env --python=python3.10
```
```
source env/bin/activate
```
```
pip install -r requirements.txt
```
Once created, we'll run the solver once and then, enable the FlaskAPI service to allow access to the json computed file (that contains all events in the correct order) to the backend (Laravel).
```
python3 solver.py
```
Now, run the FlaskAPI service:
```
cd ./web_server
```
```
python3 app.py
```

Once having the FlaskAPI service up, we'll need to enable the backend service (Laravel) with PHP 8.3.6
```
cd ../../web
```
```
composer install
```
Once installed all dependencies, now we can create a ``.env`` file by copying the `.env.example` and configuring all the standard credentials (we'll only need to set up the [database section if needed](https://www.inmotionhosting.com/support/edu/laravel/how-to-configure-the-laravel-env-for-a-database/), by default uses Sqlite3) 

Don't forget to add the DATA_URI credential with the value of the host of the FlaskAPI e.g. ``DATA_URI="http://127.0.0.1:5000/"`` if running in the same machine on port 5000.

If using in different devices, use [ngrok](https://ngrok.com/). (We used it for the demo)

```
php artisan migrate
```
```
php artisan serve
```
In another terminal, we'll launch the frontend active CSS compiling service using tailwindcss, (for development purposes)
```
cd .. && npm install
```
To recompile every time any file gets changed: 
```
npm run dev
```
To create a production css-compiled snapshot:
```
npm run build
```
Now, you're ready to go and all services are up!

You can enjoy the responsive web-app at 127.0.0.1:8000 (probably), or see the ``php artisan serve`` section and check which port is running on.


<a name="learning"></a>
## Learning 🎓
We paractised and learned  Technologies and Tools, like Python for all the backend and data processing. Laravel (php): the main framework for the web application development. Tailwind (CSS): Used for efficient and flexible styling in the web. Flask: For building the APIs. Pandas: Employed for data manipulation and analysis, and working with .csv files. OpenStreetMap: Integrated for rich mapping functionalities. Leaflet: Employed for the interactive map in our web. Ngrok: Utilized for secure tunneling to connect IPs. Also working with APIs, and little thinks like improving the quality of the readme in Github.

<a name="next"></a>
## What's next for Caixa Enginyers mes a prop
Send SMS messages to the users so they can answer the feedback forms.
Improve the feedback data collections and improving of the routes.

<a name="screen"></a>
## Screenshots
![d](https://github.com/EncryptEx/caixa-enginyers-mes-aprop/assets/95536223/b93fad29-b3df-42ad-b32f-01c0538c5c37)
![b](https://github.com/EncryptEx/caixa-enginyers-mes-aprop/assets/95536223/fef7a4ef-d813-4e4e-b888-b242d55f1764)
![e](https://github.com/EncryptEx/caixa-enginyers-mes-aprop/assets/95536223/a02c9823-6f25-44e4-a614-fea12bb827a7)
![Screenshot from 2024-05-20 14-49-31](https://github.com/ArnauCS03/caixa-enginyers-mes-aprop/assets/95536223/94d5dd20-85bc-4327-bc5e-e045c621a7bf)


<a name="license"></a>
## License ⚖️
Creative Commons Attribution Non Commercial No Derivatives 4.0 International <br><br><br>
