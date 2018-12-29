# Summary
Modified widget to support for following:

1. Ability to pass custom attributes
2. Return a custom error called 'REJECTION_ERROR'

## Configuration

### Example for passing custom attributes

```javascript
var config = {
  baseUrl: 'https://{yourOktaDomain}',
  logo: '/path/to/logo.png',
  helpSupportNumber: '(123) 456-7890',
  language: 'en',
  i18n: {
    en: {
      'primaryauth.title': 'Sign in to Acme'
    }
  },
  helpLinks: {
    help: 'https://acme.com/help'
  }
};

config.jsc='custom attribute 1';
config.hdm='custom attribute 2';

var signIn = new OktaSignIn(config);
```



### Example for handling REJECTION_ERROR

```javascript
var signIn = new OktaSignIn();

signIn.renderEl(
      function error(err) {
        alert('ERROR: ' + err);
        if (err.name === 'REJECTION_ERROR') { 
          window.location.replace("http://www.example.com/error.html");
        }
      }
    );
```
