# A Private, TLS and Auth protected Docker Registry, on Heroku

Deploy your own damn app:

1. Get an AWS bucket
2. Push this button: [![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy?template=https://github.com/gregburek/heroku-docker-registry)

A new app will be deployed to your Heroku account, using AWS s3 as a storage
backend and heroku-postgresql as the search index. Also, free bugsnag and new
relic addons will be provisioned, which may require a credit card to prove you
are not a robot.

## What is this BS?

[Docker Registry](https://github.com/docker/docker-registry) is a python
application and a python module. This repo includes it in
[`requirements.txt`](https://github.com/gregburek/heroku-docker-registry/blob/master/requirements.txt#L1),
and deploys it to Heroku as a web app.

The [nginx buildpack](https://github.com/ryandotsmith/nginx-buildpack) provides
https redirects and basic auth to control access to your registry. Details
about the nginx setup can be found on my
[heroku-tls-auth-nginx-sample](https://github.com/gregburek/heroku-tls-auth-nginx-sample)
repo.

Thanks to `app.json` and the [Heroku
Button](https://blog.heroku.com/archives/2014/8/7/heroku-button), your app is
automatically configured to use an s3 backend and a postgres db as a search
index.  The included `config.yml` file is used to wire up bugsnag api tokens
and the `DATABASE_URL` db uri.

Please file issues and send PRs.
