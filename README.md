# T7

This project was generated using [Nx](https://nx.dev).

<p style="text-align: center;"><img src="https://raw.githubusercontent.com/nrwl/nx/master/images/nx-logo.png" width="450"></p>

🔎 **Smart, Extensible Build Framework**

##  Installing Spartacus

First thing is we need yarn, not npm.

```txt
>npx create-nx-workspace@latest
npx: installed 48 in 5.089s
√ Workspace name (e.g., org name)     · clipboard
√ What to create in the new workspace · angular
√ Application name                    · cardmatch
√ Default stylesheet format           · scss
```

Try to specify the package manager on creation and then configure the workspace manager:

```
yarn create nx-workspace --package-manager=yarn
npx json -I -f workspace.json -e "this.cli.packageManager = 'yarn';
```

So:

```
npx create-nx-workspace@latest --package-manager=yarn
Name: t7
npx json -I -f workspace.json -e "this.cli.packageManager = 'yarn';
npx: installed 1 in 1.89s
json: updated "workspace.json" in-place
```

Add nx globally

```
yarn global add nx
```

```
>nx generate @nrwl/angular:app au-store --routing
'nx' is not recognized as an internal or external command,
```

Only worked with npx.  Ran this outside the t7 dir:

```
npm install -g @nrwl/cli
nx generate @nrwl/angular:app au-store --routing
```

How to add Spartacus?

```
> ng new au-store --style=scss
> ng add @spartacus/schematics@latest
```

From demo app

```
npm add @nrwl/angular
nx generate @nrwl/angular:app au-store --routing
```

```
nx serve au-store
yarn nx serve 
```

Add Spartacus
How to add the app flag?

```
Could not find project "@spartacus/schematics"
ng add @spartacus/schematics
nx add @spartacus/schematics --project=au-store
 ERROR  Cannot find target 'add' for project 'au-store'
```

```
ng add @spartacus/schematics --project=au-store
The add command requires to be run in an Angular project, but a project definition could not be found.
```

First:

```
yarn add  @spartacus/schematics
```

```
>nx list @spartacus/schematics
>  NX  Capabilities in @spartacus/schematics:
  GENERATORS
  ng-add : Install and configure spartacus
  add-spartacus-library : Install a spartacus library
  add-spartacus : Add spartacus to Angular project.
  add-pwa : Add PWA to project.
  add-ssr : Add server-side rendering.
  add-cms-component : Add a CMS component.
(angular material example: nx g @angular/material:ng-add)
```

```
nx g @spartacus/schematics:ng-add --project=au-store
Or
nx g @spartacus/schematics:add-spartacus --project=au-store
Property 'features' does not match the schema. 'Profile' should be a 'array'.
```

```
nx g @spartacus/schematics:ng-add --project=au-store
```

Might raise an issue on nx for this:

```
>nx g @spartacus/schematics:add-spartacus --project=au-store
√ Which Spartacus features would you like to set up?
Please note that for most Spartacus features to be properly configured, the Account feature is required. · Profile
Property 'features' does not match the schema. 'Profile' should be a 'array'.
```

I have added this to my dependencies.

```json
"@spartacus/schematics": "^3.4.1",
```

# Original Readme

## Adding capabilities to your workspace

Nx supports many plugins which add capabilities for developing different types of applications and different tools.

These capabilities include generating applications, libraries, etc as well as the devtools to test, and build projects as well.

Below are our core plugins:

- [React](https://reactjs.org)
  - `npm install --save-dev @nrwl/react`
- Web (no framework frontends)
  - `npm install --save-dev @nrwl/web`
- [Angular](https://angular.io)
  - `npm install --save-dev @nrwl/angular`
- [Nest](https://nestjs.com)
  - `npm install --save-dev @nrwl/nest`
- [Express](https://expressjs.com)
  - `npm install --save-dev @nrwl/express`
- [Node](https://nodejs.org)
  - `npm install --save-dev @nrwl/node`

There are also many [community plugins](https://nx.dev/community) you could add.

## Generate an application

Run `nx g @nrwl/react:app my-app` to generate an application.

> You can use any of the plugins above to generate applications as well.

When using Nx, you can create multiple applications and libraries in the same workspace.

## Generate a library

Run `nx g @nrwl/react:lib my-lib` to generate a library.

> You can also use any of the plugins above to generate libraries as well.

Libraries are shareable across libraries and applications. They can be imported from `@t7/mylib`.

## Development server

Run `nx serve my-app` for a dev server. Navigate to http://localhost:4200/. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `nx g @nrwl/react:component my-component --project=my-app` to generate a new component.

## Build

Run `nx build my-app` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `nx test my-app` to execute the unit tests via [Jest](https://jestjs.io).

Run `nx affected:test` to execute the unit tests affected by a change.

## Running end-to-end tests

Run `ng e2e my-app` to execute the end-to-end tests via [Cypress](https://www.cypress.io).

Run `nx affected:e2e` to execute the end-to-end tests affected by a change.

## Understand your workspace

Run `nx dep-graph` to see a diagram of the dependencies of your projects.

## Further help

Visit the [Nx Documentation](https://nx.dev) to learn more.



## ☁ Nx Cloud

### Distributed Computation Caching & Distributed Task Execution

<p style="text-align: center;"><img src="https://raw.githubusercontent.com/nrwl/nx/master/images/nx-cloud-card.png"></p>

Nx Cloud pairs with Nx in order to enable you to build and test code more rapidly, by up to 10 times. Even teams that are new to Nx can connect to Nx Cloud and start saving time instantly.

Teams using Nx gain the advantage of building full-stack applications with their preferred framework alongside Nx’s advanced code generation and project dependency graph, plus a unified experience for both frontend and backend developers.

Visit [Nx Cloud](https://nx.app/) to learn more.
