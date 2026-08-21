# Upskill Web

Angular 17 web frontend for the existing Upskill backend.

The current implementation includes a responsive email login and four-digit
OTP verification flow. It intentionally uses `any` for application data and
has strict TypeScript checking disabled.

## Run locally

1. Run `npm install`.
2. Set the backend host in `src/environments/environment.ts`.
3. Run `npm start`.
4. Open `http://localhost:4200`.

## Authentication API flow

- Request OTP: `POST /upskill-api/auth/getEmailOtp` with `{ email }`
- Verify OTP: `POST /upskill-api/auth/verifyEmailOtp` with `{ email, otp }`
- Successful verification is stored in `localStorage` as `upskill_session`.

## API configuration

Set the backend host in `src/environments/environment.ts`:

```ts
apiBaseUrl: 'http://localhost:5000'
```

Do not include `/upskill-api` or a trailing slash. All backend paths are
centralized in `src/app/core/services/api-routes.service.ts`.

Example:

```ts
constructor(private readonly routes: ApiRoutesService) {}

// http://localhost:5000/upskill-api/user/getStudentDetails
this.routes.user.getStudentDetails;
```

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 17.3.17.

## Development server

Run `npm start` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
