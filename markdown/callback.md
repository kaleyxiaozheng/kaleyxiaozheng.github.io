A **callback** is a function that is passed into another function as an argument to be executed later.  
Callbacks are used in two different ways - in synchronous functions and asynchronous functions

> If the code execurtes in top to bottom, left to right fashion, sequentially, and waiting until one code has finished before the next line begins, then the code is synchronous.
>
> Callbacks are used in synchronous functions when you want a part of the code to be easily swapped with something else.
>
> Asynchronous means no block. the rest of the codes will be execuuted while waiting for something to complete.

The **Event loop**

> - Todo-list -> Call stack
> - Waiting-list -> Web apis
> - Mental note -> Event queue

Common uses of callbacks to tell JavaScript what to do:

> 1. When an event fires (like addEventListener)
> 2. After AJAX calls (like jQuery.ajax)
> 3. After reading or writing to files (Like fs.readFile)
>
> ```
> // Callbacks in event listeners
> document.addEventListener(button, highlightTheButton)
> document.removeEventListener(button, highlightTheButton)
>
> // Callbacks in jQuery's ajax method
> $.ajax('some-url', {
>   success (data){/* success callback */},
>   error(err){/* error callback */}
> });
>
> // Callbacks in Node
> fs.readFile('pathToDirectory', (err, data)=> {
>    if(err) throw err
>    console.log(data)
> })
>
> // Callbacks in ExpressJS
> app.get('/', (reg,res) => res.sendFile(index.html))
> ```
