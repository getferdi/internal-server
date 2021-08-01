<p align="center">
    <img src="./logo.png" alt="" width="300"/>
</p>

# ferdi-internal-server
Internal Ferdi Server used for storing settings without logging into an external server.

# 🪦🪦🪦 ARCHIVED 🪦🪦🪦
This repository has been merged into the main `ferdi` repository and subsequently the standalone repo has been moved into archived mode. Please log any bugs, etc in the main repo.

## Differences to ferdi-server
- Doesn't contain user management (only one user)
- Doesn't require logging in
- No recipe creation
- Contains `start.js` script to allow starting the server via script
- Uses `env.ini` instead of `.env` to stay compatible with Ferdi's build script
- Only allows Ferdi clients to connect to the API

## Configuration
franz-server's configuration is saved inside the `env.ini` file. Besides AdonisJS's settings, ferdi-internal-server has the following custom settings:
- `CONNECT_WITH_FRANZ` (`true` or `false`, default: `true`): Whether to enable connections to the Franz server. By enabling this option, ferdi-internal-server can:
  - Show the full Franz recipe library instead of only custom recipes
  - Import Franz accounts

## Importing your Franz account
ferdi-internal-server allows you to import your full Franz account, including all its settings.

To import your Franz account, open `http://localhost:45569/import` in your browser and login using your Franz account details. ferdi-internal-server will create a new user with the same credentials and copy your Franz settings, services and workspaces.

## Development
You can locally develop ferdi-internal-server outside of Ferdi.
1. Clone this repository
2. Install dependencies via
   ```bash
   npm install
   ```
3. Start the local server via
  ```bash
  npm start
  ```
4. Change Ferdi's server to `http://localhost:45568` to start using the local test server.
