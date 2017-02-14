# @nhz.io/travis-scoped-publish

<p align="center">
  <a href="https://npmjs.org/package/@nhz.io/travis-scoped-publish">
    <img src="https://img.shields.io/npm/v/@nhz.io/travis-scoped-publish.svg?style=flat"
         alt="NPM Version">
  </a>
  
  <a href="https://travis-ci.org/nhz-io/travis-scoped-publish">
    <img src="https://img.shields.io/travis/nhz-io/travis-scoped-publish.svg?style=flat"
         alt="Travis Build">
  </a>

  <a href="https://github.com/nhz-io/travis-scoped-publish/blob/master/LICENSE">
    <img src="https://img.shields.io/github/license/nhz-io/travis-scoped-publish.svg?style=flat"
         alt="License">
  </a>
</p>
<p align="center">
    <h3 align="center">Publishing scoped modules with public assess from travis</h3>
</p>

## Configure travis
Set **NPM_AUTH_TOKEN** repository variable in travis to your npm auth token (from `~/.npmrc`)

## Modify the .travis.yml below to your needs
```yml
language: node_js

deploy:
  - provider: script
    script: echo "//registry.npmjs.org/:_authToken=$NPM_AUTH_TOKEN" > ~/.npmrc 2>/dev/null
    on:
      tags: true

  - provider: script
    script: npm publish --access public
    on:
      tags: true
```

## License [MIT](LICENSE)