- A ***code*** is exchanged for a ***token**.
	- This is to ensure the token does not get in the URI and saved in history.
	- The code is just for the callback.


So the attack is:

You put in the callback:

`bank.com/login?user=attacker&code=secret-stuff` 

Without a "State", it will just login as attacker.

But there is a Cookie/Server session that the attacker called "state" the attack must match for the request to be valid. They can't access these. 


## PKCE

- A random string is generated call a "code verifer"
- This then generates a base64 sha256 hash called the "code challenge"