[comment]: <> (CTRL + SHIF + V to preview markdown in VSCode)

# tremdgol-backend

REST API that provides soccer matches statistics to others applications. Currently these three apps are consuming data from this project:

- [Tremdgol.com (Vue)](https://github.com/jvictorjs/tremdgol)
- [Tremdgol Android App (React Native)](https://github.com/jvictorjs/tremdgol-app)
- [Bolanarede.net.br (Angular)](https://github.com/jvictorjs/bolasite)

## How it works?

![TremdGol backend flow (1)](https://user-images.githubusercontent.com/28718999/197030296-961e65f3-e013-4cb2-b88c-9fdc9425e373.png)
Bsportsfan token (30usd for 3600 reqs/hour) ➡️ Google apps script trigger to update database ➡️ Tremdgol api (data available with no restrictions to my apps)

The origin of the data is a paid service (bsportsfan.com), which provides me an access token with the limitation of 3600 requests per hour for 30 USD/month.

To avoid inserting this key directly into any application code, I created my own backend to work as a data cache and make it available for all applications that I want to use. Publishing the paid token is a flaw that could easily exceed the request per hour limit, interrupting the collection of information.

To keep this database updated, I created some Google Apps Script triggers, running 24/7.

### Language

English

## Techs

- [JSON Server](https://www.npmjs.com/package/json-server)
- [Digital Ocean](https://www.digitalocean.com/)
- [Certbot SSL](https://certbot.eff.org/)
- REST APIs

## It is online!

https://api.tremdgol.com
