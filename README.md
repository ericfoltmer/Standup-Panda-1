  _________ __                     .___             __________                    .___       
 /   _____//  |______    ____    __| _/_ ________   \______   \_____    ____    __| _/____   
 \_____  \\   __\__  \  /    \  / __ |  |  \____ \   |     ___/\__  \  /    \  / __ |\__  \  
 /        \|  |  / __ \|   |  \/ /_/ |  |  /  |_> >  |    |     / __ \|   |  \/ /_/ | / __ \_
/_______  /|__| (____  /___|  /\____ |____/|   __/   |____|    (____  /___|  /\____ |(____  /
        \/           \/     \/      \/     |__|                     \/     \/      \/     \/ 

# StandupPanda

A [Slack](https://slack.com/) bot that runs daily standups for Equinox.

![screenshot](screenshot.png)

## Installation (Docker)

1. Clone the repo
2. Install the latest version of [Docker Toolbox](https://www.docker.com/toolbox) for local development and testing
3. Run `docker-compose up` to build the container
4. Environment variables can be set via the `.env` file (a sample `.env.example` file is included)

The container itself can be deployed to any Docker compatible host.

5. Set up some config variables using the .env.example:
   - `TOKEN`: your team's Slack API token. (required)
   - `USERNAME`: your bot's username. (optional; defaults to `'Standup Panda'`)
   - `ICON_EMOJI`: the emoji used in the bot's icon. (optional; defaults to `':panda_face:'`)
   - `CHANNEL`: the channel in which you stand up. (optional; defaults to `'#standup'`)
   - `IGNORE_USERS`: a string representing a comma-separated array of strings representing active channel users who never stand up. (eg `'["username1", "username2"]'`; optional; defaults to `'["heytaco"]'` ignorning heytaco bot. Hint: ignore all bot users in channel :)
   - `INIT_GREETING`: the way Standup Panda greets you when a standup is initialized. (optional; defaults to `'Good morning'`)
   - `START_MESSAGE`: the instructions Standup Panda issues when a standup starts. (optional; defaults to `'What did you work on yesterday? What are you working on today? What, if any, are your blockers?'`)
   - `GIPHY`: a string representing a boolean of whether you want to use Giphy on queries Standup Panda doesn't understand. (optional; defaults to `FALSE`)
   - `JIRA_URL`: a link to view the relevant scrum / kanban board so users can review issues during standup (optional; defaults to `''`)
   - `BOARD_NAME`: a name for your scrum board (optional; defaults to `''`)

6. Add the URL where the web app is deployed as an [outgoing webhook](https://my.slack.com/services/new/outgoing-webhook) in Slack. Don't forget the trailing `/`!
7. Type `!standup` in your chosen channel to start a new standup. (Need help? Type `!help`.)

## Thanks
Standup Panda is a fork of [Morgenbot] https://github.com/eelzon/morgenbot. This project takes its inspiration from [tender](https://github.com/markpasc/tender), a standup bot for IRC; leaned heavily on [Slask](https://github.com/llimllib/slask) for its implementation of Flask; and uses the [Slack API](https://api.slack.com/) via the Python wrapper [Slacker](https://github.com/os/slacker). Thank you.

## Contributors
* @efoltmer
