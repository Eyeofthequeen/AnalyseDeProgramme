<h1>Run a .jj file</h1>

1. Start a terminal.

   Right click on src &rarr; Show in local terminal &rarr; Terminal

   or

   CTRL + Alt + T.

2. Compile the file.

   <code>javac *.java</code>

3. Run the parser with the name of the class.

   <code>java NameClass ""</code>
   
   
<h2> Javacc - docs </h2>

1. What is the next token ? <br>
   getNextToken() will get the next token in line and execute it with the current token. If an error occures, it won't be the right error. NOT TO USE.

   If we want to know what is the next token in line without executing it, we can use <code>getToken(1)</code> with <code>getToken(0)</code> being the current token in use.
