# Keycloak Server

This directory contains a `docker-compose.yml` file to run a Keycloak server for Single Sign-On (SSO).

## How to use

1.  **Start the server:**
    Open a terminal in this directory and run the following command:
    ```bash
    docker-compose up -d
    ```
    This will start the Keycloak server in the background.

2.  **Access the Admin Console:**
    Once the server is running, you can access the Admin Console at the following URL:
    [http://localhost:8080/admin](http://localhost:8080/admin)

3.  **Login:**
    Use the following credentials to log in:
    *   **Username:** `admin`
    *   **Password:** `admin`

**Note:** These are the default credentials for development purposes. For a production environment, it is highly recommended to change the admin password. You can do this in the `docker-compose.yml` file by changing the `KC_BOOTSTRAP_ADMIN_PASSWORD` environment variable.

## Integrating with Applications

To integrate your applications with Keycloak, you will need to register them as clients in your Keycloak realm. Here is a general overview of the process:

1.  **Create a client:** In the Keycloak Admin Console, navigate to your realm, and then to the "Clients" section. Create a new client for your application.
2.  **Configure the client:** You will need to configure the client with the correct settings for your application, such as the valid redirect URIs.
3.  **Use a Keycloak adapter or OIDC library:** In your application, you can use a Keycloak adapter or a generic OpenID Connect (OIDC) library to handle the authentication flow. These libraries will redirect users to Keycloak to log in, and then handle the tokens that Keycloak issues.

For detailed instructions on how to secure different types of applications, please refer to the official Keycloak documentation:

*   **[Securing Applications and Services Guide](https://www.keycloak.org/guides#securing-apps)**

This guide provides specific examples for various platforms and programming languages.