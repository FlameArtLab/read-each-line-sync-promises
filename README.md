# Read each line synchronously with JS promises 

Read file line by line synchronously in Promise style.

## Install

    npm install FlameArtLab/read-each-line-sync-promises

## Example

```javascript
var readEachLineSync = require('read-each-line-sync-promises')

readEachLineSync('test.txt', 'utf8', async function (line) {
  
  console.log(line)
  
  if(await LongOperation) 
    return false; // Stop reading
  else
    return true; // Continue reading
  
}).then(()=> {
    ...
})
```

Encoding can optionally be omitted, in which case it will default to utf8:

```javascript
readEachLineSync('test.txt', function(line) {
  console.log(line)
})
```

End-Of-Line can be specified along with encoding if necessary, otherwise it defaults to your operating system EOF:

```javascript
readEachLineSync('test.txt', 'utf-8', '\n', function(line) {
  console.log(line)
})
```


## Credits

Author: [FlameArt](https://github.com/FlameArtLab)

Based on `read-each-line-sync` by [Geza Kovacs](http://github.com/gkovacs)

Based on [readLineSync](https://gist.github.com/Basemm/9700229)

## License

MIT
