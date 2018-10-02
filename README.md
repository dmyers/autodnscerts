# Dehydrated Config

For Namesilo DNS.

### Config

Files taken from example Lexicon DNS setup and configured for Namesilo:
https://github.com/lukas2511/dehydrated/tree/master/docs/examples

### Environment

Add vars to environment (.bashrc):

```
export LEXICON_NAMESILO_TOKEN='XXX'
#export PROVIDER=namesilo
#export PROVIDER_UPDATE_DELAY=960
```

*** Takes 16 minutes (960 seconds) for them to update DNS zone files. ***

### Run

```
/path/to/dehydrated -c
```

Other args:
* cron mode -> --cron or -c
* custom hook -> --hook /path/to/hook.sh
* challenge -> --challenge (dns-01 or http-01)

### Cron

Setup as cron job to run on the first every month to renew cert.

```
crontab -e
0 1 1 * * /path/to/dehydrated -c
```
