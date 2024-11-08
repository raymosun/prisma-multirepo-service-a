This is a repo for testing sharing one prisma schema between multiple microservice repos via git submodules. The main repo is [here](https://github.com/raymosun/prisma-multirepo).

### Setup

1. Run `yarn install` to install dependencies
1. Run `git submodule update --init` to initialize the subrepo "prisma" (which holds the schema)
1. Copy `.env.example` to `.env` and fill in the DB string
1. Run `yarn run prisma:generate` to generate prisma client

### Updating submodule

1. `cd prisma` (into the submodule)
1. Fetch and checkout commit you want, or pull origin main
1. `cd ..` (back to service repo)
1. Commit `/prisma` (this will just update the commit reference in this repo)