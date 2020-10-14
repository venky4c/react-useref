>useRef hook intrigued me a lot until I found this project, which explains clearly what it means. The text-book definition for useRef goes like this:

To get access to the DOM, you need to ask React to give you access to a particular DOM node when it renders your component. The way this happens is
through a special prop called `ref`.

>useEffect: If you don't need to interact with the DOM at all or your DOM changes are unobservable (seriously, most of the time you should use this).

The below diagram explains the concept. 
![Alt Text](https://github.com/venky4c/react-useref/blob/master/src/ReactLifeCycle.jpg)

```javascript
const inputRef = useRef(null);//Now that we have added a reference to our input element, we can use that reference to set focus.
  //However, we can’t just set focus to the element directly in out App function. We have to wait until the rendering has completed.

  useEffect(() =>{
    //We can do that with the useEffect hook. With useEffect, the code inside will run after the component has rendered. 
    //We can focus the input element by executing the focus function on the current object.
    inputRef.current.focus();
  })
  return (
    <>
    <input
      className="__dml_text-field"
      ref={inputRef}      
    />
```
