Hopscotch-Translations
======================

App for interacting with gengo to translate Hopscotch localizable.strings files


# Note: if you are experiencing errors, the first thing to check is whether you are out of money on Gengo

### Getting Started

1. Do `./hs_genstrings` from the iPad app's directory to generate the new strings file.
2. Add the english Localizable.strings to s3 in `hopscotchtranslations/production/en.lproj`
3. Make sure the permissions allow reading by anyone
4. `heroku run rake db:seed` to seed your database from the Localizable.strings files in s3
5. `heroku run rake gengo:translate` to translate all the new words that are not translated yet
6. Wait for stuff to be translated
7. `heroku run rake gengo:sync_all`
8. `heroku run rake localizable_strings:write`
9. Now your translations should be in the AWS bucket.
10. Everything should be translated now, if not start reading the code! 

### Translating Release Notes
* Get heroku access from Sam and set up heroku as a remote 
* Add the release notes to the translations website (form at the end of the english words list)
* `heroku run rake gengo:translate`
* Wait for translations to finish
* Check on https://gengo.com/c/dashboard/ that the translations are finished (get username and password from Sam)
* `heroku run rake gengo:sync_all`


### Setting up translations locally.
* Make sure you set up config/application.yml (Ask Sam for help)
