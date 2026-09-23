# MediaVault
MediaVault is a desktop media library application built using JavaFX and SQLite to help users organize and browse their personal collections of songs, games, and series in one place. This project started as command-line based and evolved into a full graphical application.
## Features
- **Unified Media Library** - catalogs songs, games, and series in a single application
- **External API Integration:**
	- **SPOTIFY API**
	- **IGDB API**
	- **TMDB API**
- **Local persistence** - all library data stored in a local SQLite database
- **Search and browse** - look up and filter items across your media collection
- **Scene-based navigation** - multiple views/screens managed through JavaFX's scene graph
## Architecture
MediaVault utilizes a DAO (Data Access Object) structure combined with the MVC (Model-View-Controller) design pattern. 
- **Model** - classes representing the media items (songs, games, series) and their data
- **DAO Layer** - handles all CRUD operations between the models and the SQLite database
- **View (FXML)** - JavaFX FXML files defining the UI layout of the program
- **Controller** - handles all user interaction, binds view components to data, and coordinates calls to the DAO layer
### Project Structure
```
.
├── data/           # SQLite database
├── lib/            # JavaFX, JDBC, JSON libraries
└── src/
	├── application/        
	│   ├── api/              # Spotify, TMDB, GameBrain API clients
	│   ├── controller/       # JavaFX controllers (one per FXML scene)
	│   ├── dao/              # Data Access Objects for SQLite db
	│   ├── db/               # Database connection and initialization
	│   ├── model/            # Data classes (Song, Movie, Game, etc.)
	│   ├── view/ (resources) # Abstract classes for shared scenes
	│   └── Main.java         # Main driver file
	└── resources/            # Resource files (css, icons, fonts, etc.)
```
## Tools Used
- **Language:** Java
- **UI:** JavaFX
- **Database:** SQLite
- **External APIs:** Spotify, IGDB, TMDB
### Database
MediaVault uses a local SQLite database, with all tables managed through the DAO layer to keep SQL isolated from UI and business logic.
#### Core Tables
- **`users`** — accounts (`username`, `password`, `profile_picture`)
- **`games`** — title, creator, year, genre, image, average playtime
- **`songs`** — title, album, creator, year, runtime, image
- **`shows`** — title, creator, year range, season/episode counts, average episode length, airing status
- **`seasons`** — child of `shows`
- **`episodes`** — child of `seasons`
## Getting Started
### Running the Application
### Prerequisites
- JDK 17 or higher
- Eclipse IDE
- JavaFX SDK
## Setup (using eclipse)
1. Create a new JavaFX workspace
2. Paste the files inside the folder
	- Paste the necessary files inside
	- Make sure to include all the `.java`, `.fxml`, `.css` and `resources` folder
3. Add JavaFX to the project
	- Right click folder inside the Package Explorer
	- Go to Build Path → Configure Build Path
	- Go to Libraries → Modulepath → Add External JARs
	- Navigate to your Java SDK folder and select all .jar files
	- Click "Apply and Close"
4. Add VM arguments
	- Right-click the project → Run As → Run Configurations
	- Select your main class under Java Application
	- Go to the Arguments tab → VM Arguments
	- Add the following, replacing the path with your JavaFX SDK location: `--module-path "C:\path\to\javafx-sdk\lib" --add-modules javafx.controls,javafx.fxml`
	- Click "Apply"
5. Locate `Main.java` in the Package Explorer
6. Right-click `Main.java` → Run As → Java Application
7. The application window will open
## Contributors
- Developed collaboratively by Amiel S. Tongco and Mark Justin Villafuerte.
## License and Academic Use
- This group project was developed for the course Object-Oriented Programming (CCPROG3) at De La Salle University - Manila. It is made available as-is for portfolio and educational purposes. All rights to original coursework specifications and course materials remain with the institution.
