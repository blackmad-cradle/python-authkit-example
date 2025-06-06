# Python integration example using AuthKit

An example application demonstrating how to authenticate users with AuthKit, Flask and the WorkOS Python SDK.

> Refer to the [User Management](https://workos.com/docs/user-management) documentation for reference.

## Prerequisites

You will need a [WorkOS account](https://dashboard.workos.com/signup).

## Requirements

Python 3

## Running the example

1. In the [WorkOS dashboard](https://dashboard.workos.com), head to the Redirects tab and create a [sign-in callback redirect](https://workos.com/docs/user-management/1-configure-your-project/configure-a-redirect-uri) for `http://localhost:3000/callback`.

2. After creating the redirect URI, navigate to the API keys tab and copy the _Client ID_ and the _Secret Key_. Rename the `.env.example` file to `.env` and supply your Client ID and API key as environment variables.

3. Additionally, create a cookie password as the private key used to encrypt the session cookie. Copy the output into the environment variable `WORKOS_COOKIE_PASSWORD`.

   It has to be exactly 32 characters long. You can use https://1password.com/password-generator/ to generate strong passwords. Alternatively, use the OpenSSL library to generate a secure password:

   ```bash
   openssl rand -base64 24
   ```

4. Verify your `.env` file has the following variables filled.

   ```bash
   WORKOS_CLIENT_ID=<YOUR_CLIENT_ID>
   WORKOS_API_KEY=<YOUR_API_SECRET_KEY>
   WORKOS_REDIRECT_URI=http://localhost:3000/callback
   WORKOS_COOKIE_PASSWORD=<YOUR_COOKIE_PASSWORD>
   ```

5. Install the dependencies

   ```bash
   pip install -r requirements.txt
   ```

6. Run the following command and navigate to [http://localhost:3000](http://localhost:3000).

   ```bash
   python app.py
   ```
