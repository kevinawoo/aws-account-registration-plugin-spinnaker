## Spinnaker Plugin for Dynamic Account Registration

### Usage
1. Run `./gradlew releaseBundle` in the root of this project. 
2. The above command will create a zip file, `build/distributions/spinnaker-aws-account-registration*.zip`.
3. Copy the zip file to Clouddriver plugin directory. Defaults to `/opt/clouddriver/plugins`. This directory can be 
specified by the `plugins-root-path` configuration property.
4. Enable the plugin by placing the following in [Clouddriver profile](https://spinnaker.io/reference/halyard/custom/#custom-profiles)

```yaml
spinnaker:
  extensibility:
    plugins-root-path: /opt/clouddriver/plugins
    plugins:
      AWS.AccountRegistration:
        enabled: true
    repositories: {}
    strict-plugin-loading: false
```

### Available configuration properties:
```yaml
accountProvision:
  url: 'http://localhost:8080/hello' # Remote host address. 
  pullFrequencyInMilliSeconds: 10000 # How often this plugin should query the remote host.
  syncAgentFrequencyInMilliSeconds: 10000 # How often agent scheduler should run.
```

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This project is licensed under the Apache-2.0 License.

