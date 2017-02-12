## Resources

- [W3Schools Guide to AJAX](http://www.w3schools.com/xml/ajax_intro.asp) --- the whole thing is useful, but in particular:
  - W3Schools Guide to the XMLHttpRequest Object
  - W3Schools Guide to Sending a Request to a Server
- [Great video about the event loop (clickme)](https://www.youtube.com/watch?v=8aGhZQkoFbQ)
- [HTTP: The Protocol Every Web Developer Must Know](http://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-1--net-31177)
- [Codeacademy API course](https://www.codecademy.com/learn/ibm-watson)
- [cool API list you could use for the project](https://market.mashape.com/explore)
- [Mozilla dev network XHR request guide](https://developer.mozilla.org/en/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest)

## Abstraction

Writing the normal XHR request is long and hard to read. Think about abstracting
away all the complexity.

Create a function `request` which performs the XHR.

```js
function request (url, cb) {
  var xhr = new XMLHttpRequest();
  xhr.onreadystatechange = function() {
    if (xhr.readyState === 4 && xhr.status === 200) {
      cb(null, xhr.responseText);
    } else {
      console.log("waiting for response");
    }
  };
  xhr.open("GET", url, true);
  xhr.send();
}
```