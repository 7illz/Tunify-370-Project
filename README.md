# Tunify

<p align="center">
  <img src="tunify.png" alt="Tunify logo" width="180">
</p>

Tunify is a browser-based music streaming application built with PHP and MySQL. It lets listeners create accounts, explore songs, albums, and artists, maintain personal playlists, discover popular public playlists, and manage a subscription from a responsive web interface.

## Features

- Account registration, login, logout, profile editing, and account deletion
- Song, album, and artist browsing
- Song and album search
- In-browser audio playback and listen-count tracking
- Personalized song recommendations based on playlist genres
- Private or public playlist creation and management
- Add songs to playlists and remove them later
- Public playlist discovery and likes
- Free, Premium, and Family subscription options
- Responsive interface styled with CSS and Google Fonts

## Tech stack

- PHP with sessions and MySQLi
- MySQL or MariaDB
- HTML5 and CSS3
- Vanilla JavaScript
- Apache (XAMPP is the simplest local setup)

## Getting started

### Prerequisites

- [XAMPP](https://www.apachefriends.org/) or an equivalent Apache/PHP/MySQL environment
- PHP with the MySQLi extension enabled
- Git

### Installation

1. Clone the repository into your web server's document root. With XAMPP on Windows, that is normally `C:\xampp\htdocs`:

   ```bash
   git clone https://github.com/7illz/Tunify-370-Project.git tunify
   ```

2. Start Apache and MySQL from the XAMPP control panel.

3. Create a MySQL database named `tunify`.

4. Create and seed the tables used by the application:

   - `user`
   - `subscription_table`
   - `songs`
   - `artist`
   - `album`
   - `playlist`
   - `playlist_songs`
   - `playlist_likes`

   > The current repository does not include a database dump. The application expects an existing schema and catalog data before its database-backed pages can run.

5. Check the credentials in `database.php`. The development defaults are:

   ```text
   host: localhost
   user: root
   password: (empty)
   database: tunify
   ```

   Some playlist-related PHP files repeat these connection values and must be updated too if your local credentials differ.

6. Open [http://localhost/tunify/index.php](http://localhost/tunify/index.php), create an account, and sign in.

## Main pages

| File | Purpose |
| --- | --- |
| `index.php` | Login page |
| `signup.html` / `signup.php` | Account registration |
| `index1.php` | Authenticated home page and recommendations |
| `songs.php` | Song catalog and player |
| `album.php` | Album listing and details |
| `artists.php` | Artist listing and details |
| `playlists.php` | Personal playlist management |
| `view_playlist.php` | Playlist details and song management |
| `subscriptions.html` | Subscription selection |
| `profile.php` | Profile and account settings |

## Project structure

```text
Tunify/
|-- index.php                 # Authentication entry point
|-- index1.php                # Signed-in dashboard
|-- database.php              # Shared database connection
|-- songs.php                 # Song catalog and playback
|-- album.php                 # Albums
|-- artists.php               # Artists
|-- playlists.php             # User playlists
|-- view_playlist.php         # Playlist editor
|-- profile.php               # Account management
|-- subscriptions.html        # Subscription plans
|-- styles.css                # Application styles
|-- *.php                     # Supporting actions and endpoints
`-- images / audio            # Static media used by the demo
```

## Notes

- Several navigation links assume the project is served from `/tunify`. Use that folder name locally or update those links.
- The included `rick.MP3` file is the demo audio source used by the current player implementation.
- Database credentials are currently stored in source files for local development. Use environment-based configuration before deploying the application publicly.
- This project does not currently include an automated test suite.

## Contributing

1. Fork the repository.
2. Create a feature branch: `git switch -c feature/your-feature`.
3. Commit your changes.
4. Push the branch and open a pull request.

## License

No license has been specified for this repository. All rights remain with the project authors.
