The Katacoda editor-terminal UI Layout combines an Editor with a Terminal. When changes are made to files using the editor, they are automatically sync'ed to the user's home directory.

# Index.json

The syntax for the editor is automatically inferred from the file extension. This can be enforced by including a "uisettings"

"environment": {
    "uilayout": "vscode-terminal-split"
},
# Helper Functionality

To support users, Katacoda has integrated various features to help users.

Copy file to editor:

var http = require('http');
var requestListener = function (req, res) {
  res.writeHead(200);
  res.end('Hello, World!');
}

var server = http.createServer(requestListener);
server.listen(3000, function() { console.log("Listening on port 3000")});
The following snippet will prepend the contents of the editor:

console.log("Starting...")
Within the Markdown, include:

<pre class="file" data-filename="app.js" data-target="prepend">console.log("Starting...")
</pre>
The following snippet will append the contents of the editor:

console.log("Finishing...")
Within the Markdown, include:

<pre class="file" data-filename="app.js" data-target="append">console.log("Finishing...")
</pre>
The editor can copy to particular files based on the data-filename attribute:

console.log("Index.js here...")
Within the Markdown, include:

<pre class="file" data-filename="index.js" data-target="replace">console.log("Index.js here...")
</pre>
Using the data-target="insert" attribute you can instruct the editor to insert the text in a particular position marked by data-marker attribute.

#TODO-insert
<pre class="file" data-filename="app.js" data-target="insert" data-marker="#TODO-insert">
console.log("Inserted value using the data-marker attribute...")
</pre>
console.log("Inserted value using the data-marker attribute...")
## New Files

Create a new file via the CLI: touch newFile.js{{execute}}

The Markdown is:

`touch newFile.js`{{execute}}
This can then be opened: newFile.js{{open}}

The Markdown is:

`newFile.js`{{open}}