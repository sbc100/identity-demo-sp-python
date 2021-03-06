Sample Python SP
================

[![Build Status](https://travis-ci.org/sbc100/identity-demo-sp-python.svg?branch=master)](https://travis-ci.org/sbc100/identity-demo-sp-python)

An example service provider (SP) written in python that integrates with 18F's
identity-idp.

This is a very simply app based the `flask` and `python-saml` which
supports SAML-based SSO and SLO.

### Setup

    $ virtualenv venv
    $ pip install -r requirements.txt
    $ . venv/bin/activate

### Testing

    $ python demosp_test.py

### Running (development mode)

    $ SAML_ENV=config_local FLASK_DEBUG=1 FLASK_APP=demosp.py flask run --port=4567

### Generating a new key + self-signed cert

    openssl req -newkey rsa:2048 -nodes -keyout config/certs/sp.key \
      -x509 -out config/certs/sp.crt -config config/openssl.conf
