# RabbitJS (30 pts)



---

## Problem
All but the ```1```, ```[```, ```]```, and ```=``` keys broke on JavaScript Mage Joey’s keyboard. That didn’t stop him from trying to tell the world what he had [learnt](./files/rabbit.js), though.

## Hint
Sometimes, it’s best to leave a ~~viewpoint~~ function unevaluated.


---

That rabbit.js file [is indeed](http://patriciopalladino.com/blog/2012/08/09/non-alphanumeric-javascript.html) valid javascript.

Not really sure how the hint related to the problem. But, to solve this, we simply ran the obfuscated javascript code through node.js, hoping that it would print out the flag. The program crashed the first time, because it uses the ```alert()``` function, which is only present in the browser. We added it to our file as follows:

```
global.alert = function(x){ 
    x === 'undefined' ? console.log('undefined') : console.log(x); return; 
};
```


The program then prints out ```How deep does this rabbit hole go?```, but unfortunately that wasn't the flag =(. We then tried printing out all existing global variables with ```console.log(global);```. At the end of the printed data, we see ```f: 'flag{carroll_knew_it}'```

## Flag
```flag{carroll_knew_it}```

