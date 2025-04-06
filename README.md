
# Weather Application (Flask + Docker + PostgreSQL)

A simple web application to check the current weather for a selected city. The application uses [WeatherAPI](https://www.weatherapi.com/) to fetch weather data and stores the results in a PostgreSQL database. The entire app runs in Docker containers and can be easily launched using Docker Compose.

## Features

- Check the weather for any city.
- Fetch weather data from WeatherAPI.
- Store results in a PostgreSQL database.
- Web interface with dark mode.
- Run the application in Docker containers.

## Requirements

- Docker
- Docker Compose
- API Key from [weatherapi.com](https://www.weatherapi.com/)

## Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/weather-application.git
   cd weather-application
   ```

2. **Create a `.env` file:**

   In the root directory of the project, create a `.env` file and add the following details:

   ```env
   DATABASE_URL=postgres://postgres:password@db:5432/weather_db
   WEATHER_API_KEY=your_api_key_here
   ```

3. **Build and start the application:**

   Use Docker Compose to build and start the application:

   ```bash
   docker-compose up --build
   ```

4. **Open in browser:**

   After the application starts, open your browser and navigate to:

   ```
   http://localhost:5000
   ```

## Project Structure

```
.
├── pogoda.py              # Flask application
├── templates/
│   └── index.html         # Main HTML template
├── static/
│   └── style.css          # CSS styles (including dark mode)
├── requirements.txt       # Python dependencies list
├── Dockerfile             # Application image build
├── docker-compose.yml     # Service definitions: web + db
└── .env                   # Environment variables
```

## Database

- User: `postgres`
- Password: `password`
- Database name: `weather_db`
- Table: `weather` (automatically created)

Example data in the table:

| city    | country     | temperature | condition |
|---------|-------------|-------------|-----------|
| Warsaw  | Poland      | 14.0        | Cloudy    |

## Tips

- To inspect data in the database:

```bash
docker exec -it <postgres_container_id> psql -U postgres -d weather_db
```



## License

MIT License
