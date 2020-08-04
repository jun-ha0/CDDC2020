<h3> VulnLogin </h3>

DESCRIPTION:
This is not how you log someone in!

`http://vulnlogin.chall.cddc2020.nshc.sg:8090/`

Note:
Flag format is CDDC20{username_password}

Inspecting the source (Ctrl + Shift + I on Google Chrome) of the [link](http://vulnlogin.chall.cddc2020.nshc.sg:8090/), 
we have the following.
```
function login() {
	var username = document.forms[0].username.value;
	username = CryptoJS.MD5(username).toString();
	var password = document.forms[0].password.value;
	password = CryptoJS.MD5(password).toString();
	if (username == "200ceb26807d6bf99fd6f4f0d1ca54d4" && password == "bbb0ddff1b944b3cc68eaaeb7ac20099") {
		alert("CONGRATS! Go ahead and submit your well-earned flag ;)");
	}
	else {
		alert("Login failed! :(");
	}
}
```

Using an online MD5 decryption tool on `200ceb26807d6bf99fd6f4f0d1ca54d4` and `bbb0ddff1b944b3cc68eaaeb7ac20099` yields the flag.

Credits: `https://hashes.com/en/decrypt/hash`

Name | flag
--- | ---
VulnLogin  |  CDDC20{administrator_password12345678}
