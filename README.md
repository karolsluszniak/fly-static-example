# Fly static example

Sample Fly static website based on Dockerfile, minimal Nginx image and with Fly edge static asset caching.

## Usage

Create app with selected name - here, `mystaticapp`:

```sh
fly apps create mystaticapp
```

Replace `myapp` in `fly.toml` with your app name:

```diff
- app = "myapp"
+ app = "mystaticapp"
```

Deploy the app:

```sh
fly deploy
```

Check that it's working along with caching:

```sh
curl -v http://mystaticapp.fly.dev
```

```sh
# ...
< fly-cache-status: HIT
# ...
<html>
  <body>
    <h1>Hello!</h1>
  </body>
</html>
# ...
```
