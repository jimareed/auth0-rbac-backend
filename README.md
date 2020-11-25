# auth0-rbac-backend
Basic RBAC implimentation using React, Go and Auth0. Also requires https://github.com/jimareed/auth0-rbac. Based on https://github.com/jimareed/react-auth0-login, the samples from Auth0 and the Auth0 blog: https://auth0.com/blog/authentication-in-golang/.

Setup:
1. follow the setup instructions in: https://github.com/jimareed/auth0-rbac
2.  Update your `main.go` file with the required values from the Auth0 dashboard. There are 3 different spots that need to be updated:

```go
// main.go
// ...
aud := "YOUR_API_IDENTIFIER"
// ...
iss := "https://YOUR_DOMAIN/"
// ...  
resp, err := http.Get("https://YOUR_DOMAIN/.well-known/jwks.json")
// ...
```

Your **Identifier** is listed on the Settings tab of the API you just created in the dashboard. To find `YOUR_DOMAIN`, click on the **Quick Start** tab and scroll down to the code snippet. Copy the value for `options.Authority` and use that to replace `YOUR_DOMAIN`. Make sure you keep the trailing slash for `iss` in `main.go`.

**Run Go**

* In a separate terminal tab, grab the dependencies

```bash
go get
```

* Build and run your Go application:

```bash
go run .
```
