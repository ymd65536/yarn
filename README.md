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
CODEARTIFACT_URL="https://my_domain-111122223333.d.codeartifact.region.amazonaws.com/npm/my_repo/" && CODEARTIFACT_AUTH_TOKEN=`aws codeartifact get-authorization-token --domain my_domain --domain-owner 111122223333 --query authorizationToken --output text` && yarn config set 'npmRegistries["$CODEARTIFACT_URL"].npmAuthToken' "${CODEARTIFACT_AUTH_TOKEN}" && yarn config set 'npmRegistries["$CODEARTIFACT_URL"].npmAlwaysAuth' "true"
```
