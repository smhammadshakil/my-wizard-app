# my-wizard-app

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```


## Architecture and the approach


I have divided the application into multiple components. The first component is the ***MultiStep*** which will include all other steps components. I have separated each step into a separate component. All four-step components are imported into the ***Multistep*** component. Now we have four more component:

WelcomePage
- From where the wizard kick-off.

Step one 
- Where the user will insert basic information about age, name, etc.
- A USer can also check multiple plans and can see the total premium.

Step two
- Where users can verify their information and can buy insurance.

ErrorPage
- User can be prompted with an error.

To move data from ***Stepone*** to ***Steptwo*** component I have to save data into the ***Multistep*** component, using the function ***saveInfo***.

To navigate through wizard I have used the function ***next*** whose param could be a
positive and negative numbers based on the requirement to move forward or backward into the wizard

To disable the next button on ***Stepone*** I have used the function ***disableNext***,
so the user needs to input their name and age to proceed further.

The location has a default value of ***Hong Kong***.

The package has a default value ***Standard***.

***.action-button*** and ***.wizard-box*** CSS is defined into App.js because these CSS used thorugh out application

### Code overview
```
https://www.loom.com/share/6a1adf4b292841c0a2363cf3f462b6d8
```

### Project overview
```
https://www.loom.com/share/619943754a13401d935c66741336fce6
```
