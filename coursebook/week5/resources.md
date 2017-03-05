## Resources

On Heroku:

- [Process Types and the Procfile:](https://goo.gl/hHiCj3) these are the contracts
  between your app and heroku. You tell them *what it is* the and they will do
  everything needed to run it, now and in the future.

- [Heroku Add-ons:](https://goo.gl/XIa7dB) are services that integrate with Heroku
  quite well. They may be databases, file storage, monitoring, email, sms and more.

- [Scheduled Jobs and Custom Clock Processes:](https://goo.gl/66M8Jg) is a way
  to programatically run processes at specific times or intervals.

On APIs:

- [Google Sheets:](https://developers.google.com/sheets/)
- [CodeWars:](https://dev.codewars.com/)
- [Facebook Messenger:](https://developers.facebook.com/docs/messenger-platform)
- [Twilio:](https://www.twilio.com/)

### How to set up CodeClimate

Following the simple steps to set up test coverage on CodeClimate.

- Check out the link to the [documentation](https://docs.codeclimate.com/docs/setting-up-test-coverage).
- Go to test coverage troubleshoot
- Got JavaScript link
- Generate coverage data in Lcov format
- Install `codeclimate-test-reporter`'s NPM package
- Specifying your repo token as an environment variable
- Send lcov coverage data to the codeclimate-test-reporter npm script

In the terminal run:

```
$ CODECLIMATE_REPO_TOKEN=<token> ./node_modules/.bin/codeclimate-test-reporter < ./coverage/lcov.info
```
