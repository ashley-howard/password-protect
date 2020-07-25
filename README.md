```html
<div id="password">
    <input id="password-text" type="text">
    <button id="password-btn" onclick="passwordSubmit()">Submit</button>
</div>
```

```css
body {
    overflow: hidden;
}

#password {
    position: fixed;
    width: 100%;
    height: 100%;
    background: black;
    z-index: 99;
    display: flex;
    align-items: center;
    justify-content: center;        
    }

#password>* {
    padding: 7px;
    margin: 5px;
}

#password input {
    width: 200px;
}
```

```javascript
var devPass = localStorage.getItem('dev') ? localStorage.getItem('dev') : 'no';

if (localStorage.getItem('dev') == 'yes') {
    document.getElementById('password').style.display = "none"
    document.body.style.overflow = 'auto'
}

function passwordSubmit() {
    if (document.getElementById('password-text').value == "YOUR_PASSWORD" && !localStorage.getItem('dev')) {
        document.getElementById('password').style.display = "none"
        document.body.style.overflow = 'auto'
        localStorage.setItem('dev', 'yes');
    }
}
```