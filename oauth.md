- OAuth1.0
    - Based on existing protocols such as FlickrAuth and AuthSub
    - Does not scale well (state management, temporary credentials)
- OAuth2.0
    - A standard protocol for authorization
    - Supersedes the work done on the original OAuth protocol (created in 2006)
    - Has lesser cryptographic requirements and instead requires https
    - Has better support for native desktop/mobile apps
    - Supports extending the protocol
    - Reference
        - [OAuth 2 Simplified](https://aaronparecki.com/oauth-2-simplified/)
- OpenID Connect
    - A simple identity layer built on top of the OAuth 2.0 protocol
    - Provides information about the end user in the form of an id_token
    - Verifies the identity of the user and provides basic profile information about the user.
    - Reference: https://openid.net/connect/


- OAuth 2 Roles
    - Client - The application that is attempting to get access to the user's account
    - API / Resource Server - the API server used to access the user's information
    - Authorization Server
        - presents the interface where the user approves or denies the request
        - It can be the same server as the API API server
    - User / Resource Owner
        - the person who is giving access to some portion of their account

- OAuth 2 App
    - A application at the service provider that contains redirect rules and basic info presented to the user logging in
    - Redirect urls must be https
    - The app contains a client id and secret
        - Client id is public information
        - Secret must be kept confidential

- Grant types
    - General
        - The goal of all grant types is to obtain a access token
        - [Reference](https://alexbilbie.com/guide-to-oauth-2-grants/)
    - Type: Authorization Code
        - Can be used server to server
        - /auth -> /callback -> /token
    - Type: Implicit grant
        - Was previously recommended for clients without a secret
            - Has been superseded with using the Authorization Code grant with no secret
        - A simplified flow
        - Access token is returned immediately without an extra authorization
        - [Reference](https://oauth.net/2/grant-types/implicit/)
    - Type: Password / Resource owner credentials grant
        - Username and password are exchanged directly for an access token
        - Must only be used by apps created by the service itself
    - Type: Resource owner credentials grant
    - Type: Application access / Client credentials grant
        - When a application need to act on behalf of itself rather than user
        - `grant_type=client_credentials`
    - Type: Device code
        - Uses the Device Grant (device flow) to obtain a access token with no browser or limited input capability
        - [Reference](https://oauth.net/2/device-flow/)
    - Type: Refresh Token
        - Used by clients to exchange a refresh token for a access token when the access token has expired
        - [Reference](https://oauth.net/2/grant-types/refresh-token/)

- Common uses
    - Web server apps
        - Uses authorization code flow with exposed secret
    - SPA/PWA Apps
        - Uses authorization code flow but does not expose secret
    - Mobile apps
        - Uses authorization code flow but does not expose secret
        - Auth server should implement the PKCE extension

- PKCE
    - Proof Key for Code Exchange
    - Involves the native app creating an initial random secret
    - Using that secret again when exchanging the authorization code for an access token
    - [Refeerence](https://www.oauth.com/oauth2-servers/pkce/)
