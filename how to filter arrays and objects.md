https://stackoverflow.com/questions/5072136/javascript-filter-for-objects/37616104

Taken from the above article:

### I provide here several solutions:

## 1.) Using reduce and Object.keys

## 2.) As (1), in combination with Object.assign

## 3.) Using map and spread syntax instead of reduce

## 4.) Using Object.entries and Object.fromEntries

___________________________________________________________

## 1.) Example

Object.filter = (obj, predicate) => 
    Object.keys(obj)
          .filter( key => predicate(obj[key]) )
          .reduce( (res, key) => (res[key] = obj[key], res), {} );

___________________________________________________________

## 2.) Example

Object.filter = (obj, predicate) => 
    Object.keys(obj)
          .filter( key => predicate(obj[key]) )
          .reduce( (res, key) => Object.assign(res, { [key]: obj[key] }), {} );
          
___________________________________________________________

## 3.) Example

Object.filter = (obj, predicate) => 
    Object.assign(...Object.keys(obj)
                    .filter( key => predicate(obj[key]) )
                    .map( key => ({ [key]: obj[key] }) ) );

___________________________________________________________

## 4.) Example

Object.filter = (obj, predicate) => 
                  Object.fromEntries(Object.entries(obj).filter(predicate));
                  
                 
## Another Example for use case number 4:

function toArray(obj) {
  return Object.entries(obj);
}

Expected output using toArray function above

toArray({ a: 1, b: 2 }) ➞ [["a", 1], ["b", 2]]

toArray({ shrimp: 15, tots: 12 }) ➞ [["shrimp", 15], ["tots", 12]]

toArray({}) ➞ []  

___________________________________________________________


**OTHER RESOURCES**

____________________________________________________________


