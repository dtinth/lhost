# lhost

lhost is a service that redirects requests to your local development server. It's particularly useful when integrating with services that require HTTPS URLs for callbacks or redirects.

## Usage

The base URL for lhost is: https://lhost.netlify.app

To use lhost, append your desired localhost port number and path to the base URL:

```
https://lhost.netlify.app/<port>/<path>
```

This will redirect to:

```
http://localhost:<port>/<path>
```

## Examples

1. Redirecting to a local server running on port 3000:

   ```
   https://lhost.netlify.app/3000/
   ```

   Redirects to: `http://localhost:3000/`

2. Redirecting to a specific path:

   ```
   https://lhost.netlify.app/8080/api/users
   ```

   Redirects to: `http://localhost:8080/api/users`

3. Including query parameters:

   ```
   https://lhost.netlify.app/5000/oauth/callback?code=abc123&state=xyz
   ```

   Redirects to: `http://localhost:5000/oauth/callback?code=abc123&state=xyz`

## Notes

- lhost performs a 308 Permanent Redirect. This means the HTTP method and body (if any) of the original request will be preserved when redirecting to the localhost URL.
- You can include any pathname and query string parameters in the lhost URL. These will be passed along to the localhost URL in the redirect.
- This tool does not provide any security or encryption. It simply redirects HTTPS requests to your local HTTP server.
- lhost is particularly useful for development and testing scenarios where you need to provide an HTTPS URL for callbacks or OAuth redirects while working with localhost services.
- This tool is intended for development purposes and should not be used in production environments.
- Remember that this tool only performs a redirect. Your local server must be running and accessible for the final connection to succeed.
