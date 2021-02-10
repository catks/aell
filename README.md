
# Aell

Aell let's you run commands on multiple servers querying by your host tags in your AWS Infrastructure


## Installation

To run this script you must have a ruby installed in your machine.

After that, you can install from RubyGems

```bash
gem install aell
```

## Usage

To start using aell you need a `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY` and `AWS_REGION`, after that you can set the keys as environment variables:

```bash
export AWS_ACCESS_KEY_ID=my_access_key
export AWS_SECRET_ACCESS_KEY=my_secret_access_key
export AWS_REGION=my_aws_region # (eg: us-east-1)

# OPTIONAL (when using MFA)
export AWS_SESSION_TOKEN=my_secret_session_token
```

Or set with the aell options in each command:

```bash
aell -t Application:some-app -u deploy-user --access_key_id access_key_id --secret_access_key secret_access_key --region us-east-1 -c 'echo "Hello Aell"'
```

Aell can also use aws configuration in ~/.aws/, or use a specific profile with `--profile` option, eg:


```bash
aell --profile my_other_profile -t Application:some-app -u deploy-user -c 'echo "Hello Aell"'
```

Aell use AWS tags to query the servers with the `-t`/ `--tag` flags, to know more just type `aell -h`

## TODO

 1. Separate concerns
 2. Add specs

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/catks/aell

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
