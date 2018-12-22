# PRE-POST-VALIDATION

This is a very simple to use javascript library for professionally validating the user input before `POST` request for Login and Register.

fields include `name, email, password, confirm_password `
 
# The validation checks for the following

Name must be between 2 and 30 characters
Name required
Email required and is not invalid.
Password required and must be at least 6 characters 
Confirm Password field is required 
Passwords must match.

### practical usage

Run `npm install pre-post-validation`

and then

```javascript
const validateRegisterInput = require('pre-post-validation');
// or you can import like this
import { validateRegisterInput } from 'pre-post-validation';


const validateLoginInput = require('pre-post-validation');
// or you can import like this
import { validateRegisterInput } from 'pre-post-validation';
```
The functions are called with `(data)` property which includes the user data.
and return `errors` and `isValid`.

```javascript
const router = express.Router();

router.post('/register', (req, res) => {

const { errors, isValid } = validateRegisterInput(req.body);

     if (!isValid) {

        return res.status(400).json(errors);
    }
    else {
        // add your logic after the validation passed.
    }
}

router.post('/Login', (req, res) => {

const { errors, isValid } = validateLoginInput(data);

    if (!isValid) {

        return res.status(400).json(errors);
    }
    else {
        // add your logic after the validation passed.
    }
}
```

Every time you call this function you have to do some destructuring by taking out `const { errors, isValid }` and check `isValid` property for validation.




