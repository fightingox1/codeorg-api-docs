codeorg-api - DOCS
==================

codeorg-api is an API made specifically for use in code.org's applab, in order to connect two (or more) clients to one another through a server, 
if you are interested in making any multiplayer or online functionality in applab you've come to the right place! With this documentation you can learn how to get codeorg-api working in your applab project in no time!

Features
--------

- Pre Specified unique user id's
- Sending and recieving x and y coordinates
- setting a username for the pre specified user id
- getting username
- resetting all values for refreshing server
- getting and setting player ready

Player Settings
---------------
<details><summary>get-user</summary>
  
# get-user
  
### takes 0 params, returns 1 JSON
  
<p>
  
The first thing you need to do is get your user_id, you can do this using get-user which will return either P1, P2, or higher depending on the server size, which
is pre-set in the server's code, in order to get the server-size changed temporarily for your project contact support. If there are no users available get-user
will then return FULL.

URL:
```https://codeorg-server.fightingox1.repl.co/server/get-user```

Example:
```
  startWebRequest("https://codeorg-server.fightingox1.repl.co/server/get-user", function(content) {
    user = content;
    console.log("completed " + content);
  });
```
</p>
</details>

<details><summary>set-username</summary>
  
# set-username
  
### takes 2 params, returns 1 JSON
  
<p>
  
set-username is the command used to set the username of a specific user id. It uses the user given from get-user, and it also takes another input which is what
the username would be set to, in most cases it would just be whatever the user input in the username/displayname text input but of course usecase can vary
and some people may set-username in their code with no input from the user, depending on what they need. As long as there are no errors calling set-username
will output "set username"

URL:
```https://codeorg-server.fightingox1.repl.co/server/set-username{PLAYER}[USERNAME]```
in the url player would be the user assigned from get-user, for example P1. USERNAME would be the username that is being set, for example what a user would
input in the display-name box.

Example:
```
  startWebRequest("https://codeorg-server.fightingox1.repl.co/server/set-username{"+user+"}["+getText("username_input")+"]", function(content) {
    console.log("completed " + content);
  });
```
in this example username_input would be the text input of wherever your client is setting their username.
</p>
</details>

Support
-------

If you are having issues, please let us know.
We have a mailing list located at: project@google-groups.com

License
-------

The project is licensed under the BSD license.
