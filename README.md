# Service Starter Kit: Node & React Edition

Fork this repo to easily make a node-and-react-based service that can be hosted on `#{my-service}.internal.patreon.com`

Forked from 21echoes's fork of erikras's starter kit. 21echoes's fork adds JSON-API support, db integration (incl. easy migrations) and easy heroku deploys.


## Development

1. make sure node and npm are installed
1. `npm install`
1. make sure postgres is installed
1. `psql postgres < db-init.sql >/dev/null`
1. `./migrate_local.sh`


## Deployment

### Patreon Cluster

WIP! Copy these changes, but customize to your service: https://github.com/Patreon/ansible/tree/beagle-single-pr (gonna need a fair amount of work, as this PR is for a python-based service)


### Heroku

1. Create heroku app, add heroku remote, etc.
1. Add Postgres and Redis
1. Set the following heroku config vars
    1. PG_USER: (user from heroku pg settings)
    1. PG_PASS: (password from heroku pg settings)
    1. NPM_CONFIG_PRODUCTION: false
    1. NODE_PATH: ./src
    1. NODE_ENV: production
    1. DATABASE_URL: (should already be set)
    1. REDIS_URL: (should already be set)
1. Update `src/config.js`
