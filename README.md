For when setting up your site and you want a simple temporary solution to hide your website.
Bear in mind, this isn't at all secure, it's not encrypted, and is only for aesthetic purposes.

## HTML

``` html
<div id="password-display">
    <input id="password" type="text">
    <button onclick="passwordSubmit()">Submit</button>
</div>
```

## CSS

``` css
body {
    overflow: hidden;
}

#password-display {
    position: fixed;
    width: 100%;
    height: 100%;
    background: black;
    z-index: 99;
    display: flex;
    align-items: center;
    justify-content: center;
}

#password-display>* {
    padding: 7px;
    margin: 5px;
}

#password-display input {
    width: 200px;
}
```

## JavaScript

``` javascript
var devPass = localStorage.getItem('has_access') ? localStorage.getItem('has_access') : 'no';

if (localStorage.getItem('has_access') == 'yes') {
    document.getElementById('password-display').style.display = "none"
    document.body.style.overflow = 'auto'
}

function passwordSubmit() {
    if (document.getElementById('password').value == "YOUR_PASSWORD" && !localStorage.getItem('has_access')) {
        document.getElementById('password-display').style.display = "none"
        document.body.style.overflow = 'auto'
        localStorage.setItem('has_access', 'yes');
    }
}
```
