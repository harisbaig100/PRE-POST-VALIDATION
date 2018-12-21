### js-auth-validation

This is a very simple to use javascript library for professionally validating name, email, and password field for the Login and register forms.
 
### The validation checks for the following

# Name must be between 2 and 30 characters
# Name required
# Email required and is not invalid.
# Password required and must be at least 6 characters 
# Confirm Password field is required 
# Passwords must match.

### practical usage

Run `npm install react-auth-validation`

and then

```javascript
const validateRegisterInput = require('react-auth-validation');
// or you can import like this
import { validateRegisterInput } from 'react-auth-validation';


const validateLoginInput = require('react-auth-validation');
// or you can import like this
import { validateRegisterInput } from 'react-auth-validation';
```
The functions are called with `(data)` property which includes the user data.
and return `errors` and `isValid`.

```javascript
const { errors, isValid } = validateRegisterInput(data);

const { errors, isValid } = validateLoginInput(data);

if (!isValid) {
    return res.status(400).json(errors);
  }
else {
    // your logic after the validation passed.
}
```

Every time you call this function you have to do some destructuring by taking out `const { errors, isValid }` and check `isValid` property for validation.




