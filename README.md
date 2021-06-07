# 🎵 Spotify playlist sorter

Sorting playlists into a mathematically ideal order, using graph theory.

## What?

I like building playlists, but they're a lot of work.

Avoiding sudden, jarring changes in the vibe/mood takes careful attention which I can't be bothered to give them. I want to throw a bunch of tracks together and let the tracks sort themselves out.

Thankfully, by combining a bit of graph theory with the machine learning inferred features for each track in the Spotify API, this problem can be solved automatically!

## How?

Reframing the task as a version of the [travelling salesman problem](https://en.m.wikipedia.org/wiki/Travelling_salesman_problem) where each 'city' is a point in track-feature space, we end up minimising the overall path length between tracks and creating the smoothest possible transition from one mood to another!

## Getting started

You can run the notebooks for this project in a container by running `docker compose up --build` from the `notebooks/` directory.

The container will install all of the necessary dependencies, and environment variables will be pulled in from your local `.env` file.

The logs will output a localhost URL which you should use to access jupyter, just as you normally would.

### Environment variables

You'll need to fill out the `.env.blank` file and rename it `.env` to get the project running properly.

- `SPOTIPY_CLIENT_ID` and `SPOTIPY_CLIENT_SECRET` are credentials for working with the spotify API. You'll need to go to [developer.spotify.com](https://developer.spotify.com/dashboard/) to create an app and copy over its client ID and secret.
- `PLAYLIST_ID` is the ID of the playlist you'll sort. You can find the ID of your playlist by clicking the 'share' button and getting a shareable link. The playlist ID is the code after `/playlist` in the URL, eg `https://open.spotify.com/playlist/THIS_BIT_HERE?si=NOT_THIS_BIT`
