# 🚀A Challenge!

Create a JavaScript object that will act as a fake database.

It should 
- allow us to store objects
- allow us to give objects IDs
- allow us to retrieve objects by ID
- allow us to update object values
- allow us to overwrite objects

Start with the following:

```js
var fakeDb = {
  data: [];
}
```
It should have an `add` method that adds objects to `fakeDb.data`

```js
fakeDb.add({name: 'Tony', age: 25 });
fakeDb.add({name: 'Timmy', age: 24 });
```

It should have an `all` method that returns all the added objects

> When objects are added they should get an `id` property that autoincrements!

```js
fakeDb.all()
// [{name: 'Tony', age: 25, id: 1}, {name: 'Timmy', age: 24, id: 2}];
```

It should have an `find` method that returns the object with that id.

```js
fakeDb.find(1) 
// {name: 'Tony', age: 25, id: 1}
fakeDb.find(2) 
// {name: 'Timmy', age: 24, id: 2}
```

It should have a `remove` method that removes an object with that id from the `fakeDb.data` array.

```js
fakeDb.remove(1) 
fakeDb.find(1) 
// undefined
```

It should have an `update` method that takes an id and object
and updates the corresponding object's key value pairs. 

```js
fakeDb.update(2, {name: 'Sarah'});
fakeDb.find(2) 
// {name: 'Sarah', age: 24, id: 2}
```

Update should take an optional third parameter, so that when the third parameter is present
the object should be replaced not updated. 

```js
fakeDb.find(2) 
// {name: 'Sarah', age: 24, id: 2}
fakeDb.update(2, {animal: 'Tiger'}, true)
fakeDb.find(2) 
// {animal: 'Tiger', id: 2}
```

'save' should take a string for a file name and write the data to it.

```
fakeDb.save('backup.json');
// It writes data to a file
```

It should load in data from a JSON file.

```
fakeDb.load('./fakedb.json');
```
