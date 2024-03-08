## Setup
Prereq apps to have downloaded
- [git](https://git-scm.com/downloads)

Clone the repo:
```
git clone https://github.com/SidPeddi/Weather.git
```

Download all npm packages for both client/server
```javascript
npm run setup
```

### .env file
Need two creds. Weather api and mongo connection string

#### Mongo
Log into [mongo](https://account.mongodb.com/account/login)

On the left-hand sidebar, you should see **Database Access**. Click on it and make a new user for yourself.  
1. Click on `Add New Database User`
2. Create a new user by filling out `username` and `password`  
(this will be different creds than your actual mongo account. This is gives a user access to this particular database.)

On the left-hand sidebar, you should see **Network Access**.  
Make a new access point for your IP address to get permission on using your mongodb.

Now create a `.env` file in your root directory of `mern-weather-app` and dynamically add this to your `.env`
```javascript
DB=mongodb+srv://<username>:<password>@<cluster-id>.mongodb.net/test?retryWrites=true&w=majority
```
To get the cluster ID, go to **Clusters** and click on **Connect > Connect your application** to get a more detailed view of how the DB string should look like. 

#### Weather API
Make an account at   and go to the [api keys](https://home.openweathermap.org/api_keys) section.
Copy/pasta that key to the .env file using `WEATHER_KEY` as your key
```
WEATHER_KEY=1234567890asdfjkl
```
You can now run your local.  

## Run Locally
First you must install next by
```bash
npm install next
```

Now you can run the development server:
```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

## Features
- **Current Weather Conditions:** Provides access to current weather conditions, including temperature, precipitation, wind speed, UV index, and more.
- **Forecast:** Access a 10-day weather forecast and a 24-hour forecast at your fingertips.
- **Command Menu:** Toggle the command menu with a keyboard shortcut (Shortcut: Command+J) for quick access to search functionality.
- **Intelligent Autocomplete:** Enjoy a seamless location search experience with intelligent place autocomplete suggestions powered by the Google Maps Places API, and the Google Geolocation API to obtain coordinates, ensuring accurate and up-to-date information.
- **Seamless Theme Transitions:** Switch between themes (Shortcut: T) effortlessly thanks to React Hotkeys Hook, ensuring a visually pleasing and accessible interface.
- **Interactive Map:** Navigate a dynamic map with customizable tiles, including temperature (°C), precipitation intensity (mm/s), wind speed and direction (m/s), relative humidity (%), cloudiness (%), and atmospheric pressure (hPa).
