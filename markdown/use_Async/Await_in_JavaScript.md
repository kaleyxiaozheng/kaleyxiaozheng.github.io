[How to use Async/Await in JavaScript with Example JS Code](https://www.freecodecamp.org/news/async-await-in-javascript/)

### prerequisite

> 1. Event loops
>    > JavaScriptis a single_threaded programming language which means that only one task can run at a time. It has a call stack and all the code is executed inside this call stack.
> 2. Callbacks
>    > Callback functions are those functions that have been passed to another function as an argument
> 3. Promises
>    > A promise is a value that may produce a value in the future. That value can either be resolved or unresolved.

### How does Async/Await work in JavaScript

> Async allows a program to run a function without freezing the entire program. This is done using the Async/Await keyword.
>
> Async/Await makes it easier to write promises. The keyword `async` before a function makes the function return a promise, always. And the keyword await is used inside async functions, which makes the program wait until the Promise resolves
>
> ```js script
> async function example() {
>   let promise = new Promise((resolve, reject) => {
>     setTimeout(() => resolve("done!"), 2000);
>   });
>
>   let result = await promise; // wait until the promise resolve (*)
>   alert(result); // "done!"
> }
>
> example();
> ```
>
> The function execution “pauses” at the (\*) line and resumes when the promise is fulfilled, with result becoming its result. So the code above shows “done!” in two seconds
>
> ```js script
> const movies = [
>   { title: `A New Hope`, body:`After Princess Leia, the leader of the Rebel Alliance, is held hostage by Darth Vader, Luke and Han Solo must free her and destroy the powerful weapon created by the Galactic Empire.`},
>   { title: `The Empire Strikes Back`, body: `Darth Vader is adamant about turning Luke Skywalker to the dark side. Master Yoda trains Luke to become a Jedi Knight while his friends try to fend off the Imperial fleet.` }
> ]
>
> function getMovies(){
>   setTimeout(() => {
>     movies.forEach((movie, index) => {
>       console.log(movie.title)
>     })
>   }, 1000);
> }
>
> function createMovies(movie){
>   return new Promise((resolve, reject) => {
>     setTimeout(() => {
>       movies.push(movie);
>
>       const error = false;
>
>       if(!error){
>         resolve();
>       }
>       else{
>         reject('Error: Something went wrong!')
>       }
>     }, 2000);
>   })
> }
>
> async function init(){
>   await createMovies({ title: `Return of the Jedi`, body:`Luke Skywalker attempts to bring his father back to the light side of the Force. At the same time, the rebels hatch a plan to destroy the second Death Star.`});
>
>   getMovies(); (*)
> }
>
> init();
> ```
>
> In the above example, `getMovies()` at the (\*) line is waiting for `createMovies()` to be executed in the async function.
>
> In other words, `createMovies()` is async, so `getMovies()` will only run after `createMovies()` is done
