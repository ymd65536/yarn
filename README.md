# yarn

yarn に関するメモ

## Set Up

```sh
npm install -g yarn
```

## Install

[Install](https://yarnpkg.com/cli/install)

### add Package

Add yarn package

```sh
yarn add lodash@https://github.com/lodash/lodash
```

### Install Package

Install a yarn package to the project

```sh
yarn install
```

## Version

[yarn set version](https://yarnpkg.com/cli/set/version)

### Check Version

```sh
yarn -v
```

### Set version

Install stable version

```sh
yarn set version stable
```

Install stable version

```sh
yarn set version berry
```

Install latest version

```sh
yarn set version latest
```

### List Version

```sh
yarn versions
```

## yarn config

### config set

#### Examples

- aws codeartifact npmRegistries

```sh
export AWS_DOMAIN="my_domain"
export AWS_ACCOUNT_ID=`aws sts get-caller-identity --profile {profile_name} --query 'Account' --output text` &&  echo $AWS_ACCOUNT_ID
```

```sh
aws codeartifact get-repository-endpoint --domain $AWS_DOMAIN --domain-owner $AWS_ACCOUNT_ID --repository my_repo --format npm
```

```sh
export CODEARTIFACT_URL="https://$AWS_DOMAIN-$AWS_ACCOUNT_ID.d.codeartifact.region.amazonaws.com/npm/my_repo/"
```

```sh
yarn config set npmRegistryServer "$CODEARTIFACT_URL"
```

```sh
CODEARTIFACT_AUTH_TOKEN=`aws codeartifact get-authorization-token --domain $AWS_DOMAIN --domain-owner $AWS_ACCOUNT_ID --query authorizationToken --output text` && yarn config set 'npmRegistries["$CODEARTIFACT_URL"].npmAuthToken' "${CODEARTIFACT_AUTH_TOKEN}" && yarn config set 'npmRegistries["$CODEARTIFACT_URL"].npmAlwaysAuth' "true"
```
