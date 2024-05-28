# Logging in with Bruno

Bruno is a nice OSS tool for API testing. It's got some cool features, but one of my favorites is the ability to save API responses into variables. I always forget how to do it, so I'm logging it here.

APIs often use a token response to handle logins. So I hit an access point called `/api/token/` to get an access token and a response token, then hit another endpoint called `/api/refresh/` to refresh the access token. This is a pretty standard OAuth approach.

Now here's the cool thing. In your bruno login request, open the `Vars` tab. We'll assume our API returns `access_token` and `refresh_token`. At the bottom of the page, add two variables and name them the same as the keys you're trying to capture from the API response, `access_token` and `refresh_token`. 

Good! We're all set up. Now in your API route, use `access_token` as an auth variable. Go to the `Auth` tab in your route, select "Bearer Token" from the dropdown, then add `{{access_token}}`. Now once you've logged in, you can use the other routes without having to copy and paste your token.


## Links

[Bruno](https://www.usebruno.com/)
[Vars Documentation](https://docs.usebruno.com/scripting/vars)
