> Server that listens to requests and uses the [[HTTP]] protocol to return a webpage
> Eg. Apache, Nginx, IIS and NodeJS
> They serve the webpage from a root folder that is set by the software
> Eg. Apache & Nginx root folder: `var/www/html/`

## Virtual Hosts
>Ability to host different domain names in same server based on a text configuration file

Checks the requested domain and returns the corresponding webpage or the default.
Eg. (`var/www/website1`) or (`var/www/website2`)

## Static vs Dynamic

### Static
>Website that doesn't change.
>Server sends files that have no changes done to them.

### Dynamic
>Can change with different requests
>Eg. Search page on a blog will return **different** results based on the requests
>Changes are done in the [[Web Servers#Scripting & Backend|backend]]

## Scripting & Backend
>Makes website interactive to user
>Eg. PHP, Python, Ruby, NodeJS, Perl and many more

- Interact with databases, 
- Call external services, 
- Process data from the user, and so much more. 
 
A very basic PHP example of this would be if you requested the website [http://example.com/index.php?name=adam](http://example.com/index.php?name=adam)  

If index.php was built like this:  

`<html><body>Hello <?php echo $_GET["name"]; ?></body></html>`

It would output the following to the client:

`<html><body>Hello adam</body></html>`

- Interactivity opens up a lot more **security issues** for web applications that haven't been created securely