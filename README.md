<h1>non-blocking-bcrypt-nodejs</h1>
Wrapper for <a href='https://www.npmjs.com/package/bcrypt-nodejs'>bcrypt-nodejs</a> that works on a different thread to keep the crypto actions from starving the event loop.


<h2>Limitations</h2>
works on NodeJS version 7.6+,

<h2>Installing</h2>

```
npm install non-blocking-bcrypt-nodejs --save
```

lets jump to some examples
<h2>Examples</h2>

<h2>genSalt</h2> 
<ul>
    <li><code>rounds</code> - [OPTIONAL] - the number of rounds to process the data for. (default - 10)</li>
</ul>

```javascript

const bcrypt = require('non-blocking-bcrypt-nodejs')
(async () =>{
    
    try {
        const {salt} = await bcrypt.genSalt()
    
    }
    catch(err){
        
    }
})();


```
<h2>genHah</h2> 
<ul>
   <li><code>data</code> - [REQUIRED] - the data to be encrypted.</li>
   <li><code>salt</code> - [REQUIRED] - the salt to be used in encryption.</li>
</ul>

```javascript

const bcrypt = require('non-blocking-bcrypt-nodejs')
(async () =>{
    
    try {
       const {salt} = await bcrypt.genSalt()
       const {hash} = await bcrypt.genHash(salt, 'sdsasdsafasf')
    }
    catch(err){
        
    }
})();


```

<h2>saltAndHash</h2> 
<ul>
     <li><code>data</code> - [REQUIRED] - the data to be encrypted.</li>
</ul>

```javascript

const bcrypt = require('non-blocking-bcrypt-nodejs')
(async () =>{
    
    try {
       const {hash} = await bcrypt.saltAndHash('sdsasdsafasf')

    }
    catch(err){
        
    }
})();


```


<h2>compare</h2> 
<ul>
 <li><code>data</code> - [REQUIRED] - data to compare.</li>
 <li><code>encrypted</code> - [REQUIRED] - data to be compared to.</li>
</ul>

```javascript

const bcrypt = require('non-blocking-bcrypt-nodejs')
(async () =>{
    
    try {
       const {salt} = await bcrypt.genSalt()
       const {hash} = await bcrypt.genHash(salt, 'sdsasdsafasf')
       const match = await bcrypt.compare('sdsasdsafasf', hash)

    }
    catch(err){
        
    }
})();


```

<h2>Tests</h2>

```
npm test
```



