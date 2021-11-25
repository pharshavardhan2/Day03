#### Using different types of loops to iterate over JSON:
- Consider below JS object which was parsed from a JSON data.
```js
let superheroes = {
  "squadName": "Super hero squad",
  "homeTown": "Metro City",
  "formed": 2016,
  "secretBase": "Super tower",
  "active": true,
  "members": [
    {
      "name": "Molecule Man",
      "age": 29,
      "secretIdentity": "Dan Jukes",
      "powers": [
        "Radiation resistance",
        "Turning tiny",
        "Radiation blast"
      ]
    },
    {
      "name": "Madame Uppercut",
      "age": 39,
      "secretIdentity": "Jane Wilson",
      "powers": [
        "Million tonne punch",
        "Damage resistance",
        "Superhuman reflexes"
      ]
    },
    {
      "name": "Eternal Flame",
      "age": 1000000,
      "secretIdentity": "Unknown",
      "powers": [
        "Immortality",
        "Heat Immunity",
        "Inferno",
        "Teleportation",
        "Interdimensional travel"
      ]
    }
  ]
}
```
- See below for code used to iterate over above object using different loops.
```js
// using for..in
for(let key in superheroes) {
}
```
```js
// using for..of
for(let [key, value] of Object.entries(superheroes)) {
}
```
```js
// using foreach
superheroes.foreach((key) => {
  console.log(key);
});
```

