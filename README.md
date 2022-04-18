# groupize-buildpack
A Heroku buildpack for that customizes the build environment for the Groupize application

## Configure Multiple Buildpacks
Add the buildpack to your Heroku app either using the CLI or the Heroku dashboard.

The `groupize-buildpack` generates a custom `npmrc` file and therefore needs to run before any buildpack using npm. In the following example, it runs before the `heroku/nodejs` buildpack.
```bash
$ heroku buildpacks:set --index 1 https://github.com/groupize/groupize-buildpack.git
$ heroku buildpacks:add heroku/nodejs
```

## Github Package Management Configuration

### Configure Config Var
Add the GH_PKG_TOKEN config var in Heroku with your read-only GITHUB package management token

``` bash
 $ heroku config:set 00000000-0000-0000-0000-000000000000
```

## References

The generation of a custom npmrc was derived from [Heroku Buildpack NPMRC](https://github.com/debitoor/heroku-buildpack-npmrc)

## License

While this buildpack is highly customized for the use of Groupize it is MIT Licensed. Anyone visiting this is welcome to adapt it for their purposes. See License.md for details.