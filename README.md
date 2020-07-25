```html
<div id="password">
    <input id="password-text" type="text">
    <button id="password-btn" onclick="passwordSubmit()">Submit</button>
</div>
```

```css
    #password {
        position: fixed;
        content: "In production, come back soon!";
        width: 100%;
        height: 100vh;
        background: black;
        z-index: 99;
        color: white;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 5em;
        overflow: hidden
    }
```

```javascript
var devPass = localStorage.getItem('dev') ? localStorage.getItem('dev') : 'no';

    if (localStorage.getItem('dev') == 'yes') {
        document.getElementById('password').style.display = "none"
    }

    function passwordSubmit() {
        if (document.getElementById('password-text').value == "YOUR_PASSWORD" && !localStorage.getItem('dev')) {
            document.getElementById('password').style.display = "none"
            localStorage.setItem('dev', 'yes');
        }
    }
```