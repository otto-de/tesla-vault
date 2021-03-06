# tesla-vault

A Clojure library designed to enhance your edn config with secrets stored in vault.

[![Clojars Project](http://clojars.org/de.otto/tesla-vault/latest-version.svg)](http://clojars.org/de.otto/tesla-vault)

[![Build Status](https://travis-ci.org/otto-de/tesla-vault.svg)](https://travis-ci.org/otto-de/tesla-vault)
[![Dependencies Status](http://jarkeeper.com/otto-de/tesla-vault/status.svg)](http://jarkeeper.com/otto-de/tesla-vault)


## Usage

```edn
{
 :some-db-credentials  #ts/vault ["/path/to/db/password"]
 :just-the-db-password #ts/vault ["/path/to/db/password" :password] 
}
```

For this to work two environment variables need to be present:

* `$VAULT_ADDR`:the url where vault can be found (e.g.  _https://vault.yourdomain.com_)
* `$VAULT_TOKEN`: a valid token for vault.

And you have to require the reader-function like this:
```
(:require
[de.otto.tesla.vault.vault_reader :only [read-secret]])
```

## Initial Contributors

Christian Stamm, Florian Weyandt, Carl Düvel

## License
Released under [Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0) license.
