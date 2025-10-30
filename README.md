#Crack_the_gate_ctf
- The goal of this challenge was to explore a login page and determine a hidden developer functionality.
- It also sheds some light on inspecting network requests and how to use fetch() API with special headers.


#Steps Taken
- Opened challenge
- Saw a login page with email and password field.
- Clicked ctrl shift I to use developer tools.
- Looked at the source code, and saw a ROT13 text.
- Decoded the rot13 text with cyberchef.
- Tried to attempt to log in using a random password.
- Head to network section and saw the login attempt.
- Right click the new login attempt entry and copy as fetch.
- Added the ROT13 decoded header on fetch as a key value pair.
- Entered this: .then(r => r.text()).then(t => console.log(t)); at the end of the fetch(...)
- Found the flag

#Lessons learned
- Headers can grant access to a service, just like using the username and password option.
- ROT13 shifts letters by 13. E.g A becomes N
- ROT13 can be decoded easily with tools like cyberchef.
- Network section on devtools is used to show requests sent to a server and the responses.
- copy as fetch: this copies the login request as a JS fetch(...) command.
- once fetch(...) sends a request, the response is stored in Promise.
- Promise means "waiting for the reply."
- PromiseState: "fulfilled" means the server has replied.
- .then(r => r.text()) opens the response and displays the text.
