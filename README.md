#  MAUSAM — Indian Weather Intelligence

> A personalised weather intelligence platform designed for India.

MAUSAM brings weather data, location intelligence, environmental information, alerts, personalisation, and reliability mechanisms together into a unified weather experience.

The project is built around a provider-agnostic architecture so that weather and geospatial services can be integrated, monitored, cached, and replaced without tightly coupling the application to a single provider.

---

## Team

**Team:** Iconix  
**Institution:** IICT

---

##  Features

###  Weather Intelligence

- Current weather conditions
- Hourly forecasts
- Daily forecasts
- Temperature, humidity, wind and precipitation information
- Air-quality information
- Weather condition analysis
- Thunderstorm risk estimation
- Derived flood-risk intelligence

### Location Intelligence

- Automatic GPS-based location detection
- Reverse geolocation
- Location search
- Saved locations
- Search history
- GPS accuracy information
- Movement-aware location updates
- Timezone-aware forecasts

### Personalisation

- User preferences
- Personalised weather personas
- Context-aware weather insights
- Personalised recommendations
- AI-powered weather interaction

### Alerts & Weather Intelligence

- Weather notifications
- Cyclone information
- Flood-risk intelligence
- Disaster-related weather information
- Notification management

### Maps & Environmental Information

- Interactive weather maps
- Radar interface
- Satellite imagery
- Agricultural meteorological information
- Marine weather information
- Historical weather information
- Travel-oriented weather information

### Reliability & Transparency

MAUSAM includes several mechanisms designed to improve reliability when working with external data providers:

- Provider abstraction
- Provider health monitoring
- Intelligent caching
- Stale-while-revalidate behaviour
- Fallback mechanisms
- In-flight request deduplication
- Data freshness tracking
- Data provenance
- Approximate-location fallback controls
- Derived-data transparency

---

## Architecture

MAUSAM uses a provider-agnostic weather intelligence architecture.

```text
                    ┌──────────────────────┐
                    │      MAUSAM UI       │
                    │ React + TypeScript   │
                    └──────────┬───────────┘
                               │
                               ▼
                 ┌──────────────────────────┐
                 │ Weather Intelligence     │
                 │         Engine           │
                 └────────────┬─────────────┘
                              │
             ┌────────────────┼────────────────┐
             ▼                ▼                ▼
      ┌──────────────┐ ┌──────────────┐ ┌──────────────┐
      │   Provider   │ │    Cache     │ │   Fallback   │
      │    Layer     │ │   Manager    │ │   Manager    │
      └──────┬───────┘ └──────────────┘ └──────────────┘
             │
      ┌──────┼────────┬───────────┬────────────┐
      ▼      ▼        ▼           ▼            ▼
   Open-   Nominatim NASA GIBS  Copernicus   Other
   Meteo
