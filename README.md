<p align="center">
  <img alt="Cypress Real World App Logo" src="./src/svgs/rwa-logo.svg" />
</p>

<p align="center">
  <a href="https://cypress.io">
    <img width="140" alt="Cypress Logo" src="./src/svgs/built-by-cypress.svg" />
    </a>
</p>

<p align="center">
   <a href="https://cloud.cypress.io/projects/7s5okt/runs">
    <img src="https://img.shields.io/endpoint?url=https://cloud.cypress.io/badge/detailed/7s5okt/develop&style=flat&logo=cypress" />
  </a>

  <a href="https://codecov.io/gh/cypress-io/cypress-realworld-app">
    <img src="https://codecov.io/gh/cypress-io/cypress-realworld-app/branch/develop/graph/badge.svg" />
  </a>

  <a href="https://percy.io/cypress-io/cypress-realworld-app">
    <img src="https://percy.io/static/images/percy-badge.svg" />
  </a>

   <a href="#contributors-">
    <img src="https://img.shields.io/badge/all_contributors-6-green.svg?style=flat" />
  </a>
</p>

<p align="center">
A payment application to demonstrate <strong>real-world</strong> usage of <a href="https://cypress.io">Cypress</a> testing methods, patterns, and workflows.
</p>

<p align="center">
  <img style='width: 70%' alt="Cypress Real World App" src="./public/img/rwa-readme-screenshot.png" />
</p>

> 💬 **Note from maintainers**
>
> This application is purely for demonstration and educational purposes. Its setup and configuration resemble typical real-world applications, but it's not a full-fledged production system. Use this app to learn, experiment, tinker, and practice application testing with Cypress.
>
> Happy Testing!

---

## Features

🛠 Built with [React][reactjs], [XState][xstate], [Express][express], [lowdb][lowdb], [Material-UI][material-ui] and [TypeScript][typescript]
⚡️ Zero database dependencies
🚀 Full-stack [Express][express]/[React][reactjs] application with real-world features and tests
👮‍♂️ Local Authentication
🔥 Database Seeding with End-to-end Tests
💻 CI/CD + [Cypress Cloud][cypresscloud]

## Getting Started

The Cypress Real-World App (RWA) is a full-stack Express/React application backed by a local JSON database ([lowdb]).

The app is bundled with [example data](./data/database.json) (`data/database.json`) that contains everything you need to start using the app and run tests out-of-the-box.

> 🚩 **Note**
>
> You can login to the app with any of the [example app users](./data/database.json#L2). The default password for all users is `s3cret`.
> Example users can be seen by running `yarn list:dev:users`.

### Prerequisites

This project requires [Node.js](https://nodejs.org/en/) to be installed on your machine. Refer to the [.node-version](./.node-version) file for the exact version.

[Yarn Classic](https://classic.yarnpkg.com/) is also required. Once you have [Node.js](https://nodejs.org/en/) installed, execute the following to install the correct version of `yarn`.

```bash
npm install yarn -g
```

The following command allows you to check that you have Yarn Classic (version 1) installed and active:

```bash
yarn -v
```

**This project is not compatible with [Yarn Modern](https://yarnpkg.com/) (version 2 and later).**

TypeScript will be added as a local dependency to the project, so no need to install it.

### Installation

```shell
yarn
```

#### Mac users with M-series chips will need to prepend `PUPPETEER_SKIP_CHROMIUM_DOWNLOAD=true`.

```shell
PUPPETEER_SKIP_CHROMIUM_DOWNLOAD=true yarn install
```

### Run the app

```shell
yarn dev
```

> 🚩 **Note**
>
> The app will run on port `3000` (frontend) and `3001` (API backend) by default. Please make sure there are no other applications or services running on both ports.
> If you want to change the default ports, you can do so by modifying `PORT` and `REACT_APP_BACKEND_PORT` variables in `.env` file.
> However, make sure the modified port numbers in `.env` are not committed into Git since the CI environments still expect the application to run on the default ports.

### Start Cypress

```shell
yarn cypress:open
```

> 🚩 **Note**
>
> If you have changed the default ports, then you need to update Cypress configuration file (`cypress.config.js`) locally.
> There are three properties that you need to update in `cypress.config.js`: `e2e.baseUrl`, `env.apiUrl`, and `env.url`.
> The port number in `e2e.baseUrl` corresponds to `PORT` variable in `.env` file. Similarly, the port number in `env.apiUrl` and `env.url` correspond to `REACT_APP_BACKEND_PORT`.
> For example, if you have changed `PORT` to `13000` and `REACT_APP_BACKEND_PORT` to `13001` in `.env` file, then your `cypress.config.js` should look similar to the following snippet:
>
> ```js
> {
>   env: {
>     apiUrl: "http://localhost:13001",
>     codeCoverage: {
>       url: "http://localhost:13001/__coverage__"
>     },
>   },
>   e2e: {
>     baseUrl: "http://localhost:13000"
>   }
> }
> ```
>
> Avoid committing the modified `cypress.config.js` into Git since the CI environments still expect the application to be run on default ports.




