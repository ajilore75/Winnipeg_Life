# Base44 Setup Notes

## Project Overview
Single-file static web app (`html.htm`) — "Winnipeg Life: Playbook and Game". Pure HTML/CSS/JS, no backend, no build step, no dependencies.

## How It Runs
Served by an `nginx:alpine` container via `docker-compose.base44.yml`. The HTML file is bind-mounted read-only into the container's web root. Port 3000 maps to nginx's port 80.

## Verification
- `curl http://localhost:3000/` returns HTTP 200 with the HTML content.
- No secrets or external credentials needed.
- No database, no migrations, no seeds.

## Editing
Edit `html.htm` directly — changes appear immediately on reload (nginx serves the file from the bind mount, so no rebuild needed). Call `reload_preview` after edits.
