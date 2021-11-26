#### Using different types of loops to iterate over JSON:
- Consider below JS object which was parsed from a JSON data. I have given code and output for each case. So just copy it.
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
console.log("Here are my favourite superhero squad details:\n");
for(let key in superheroes) {
  if(key == "members") {
    let members = superheroes.members;
    console.log("Squad memebers are:\n");
    for(let i = 0; i < members.length; i++) {
      console.log(`\t${members[i].name}, age ${members[i].age} with secret identity ${members[i].secretIdentity}`);
      console.log("\tHis/her powers are: " + members[i].powers.join(", ") + "\n");
    }
  } else {
  	console.log(`${key}: ${superheroes[key]}\n`);
  }
}
```
```js
// using for..of
console.log("Here are my favourite superhero squad details:\n");
for(let [key, value] of Object.entries(superheroes)) {
  if(key == "members") {
    console.log("Squad members are:\n");
    for(let i = 0; i < value.length; i++) {
      console.log(`\t${value[i].name}, age ${value[i].age} with secret identity ${value[i].secretIdentity}`);
      console.log("\tHis/her powers are: " + value[i].powers.join(", ") + "\n");
    }
  } else {
    console.log(`${key}: ${value}\n`);
  }
}
```
```js
// using forEach
console.log("Here are my favourite superhero squad details:\n");
Object.entries(superheroes).forEach(([key, value]) => {
  if(key == "members") {
    console.log("Squad members are:\n");
    for(let i = 0; i < value.length; i++) {
      console.log(`\t${value[i].name}, age ${value[i].age} with secret identity ${value[i].secretIdentity}`);
      console.log("\tHis/her powers are: " + value[i].powers.join(", ") + "\n");
    }
  } else {
    console.log(`${key}: ${value}\n`);
  }
});
```
- Below is the output in each case
```
Here are my favourite superhero squad details:

squadName: Super hero squad

homeTown: Metro City

formed: 2016

secretBase: Super tower

active: true

Squad memebers are:

	Molecule Man, age 29 with secret identity Dan Jukes
	His/her powers are: Radiation resistance, Turning tiny, Radiation blast

	Madame Uppercut, age 39 with secret identity Jane Wilson
	His/her powers are: Million tonne punch, Damage resistance, Superhuman reflexes

	Eternal Flame, age 1000000 with secret identity Unknown
	His/her powers are: Immortality, Heat Immunity, Inferno, Teleportation, Interdimensional travel

```

#### My resume as JSON:
```yaml
{
  "name": "Harshavardhan reddy pathapalli",
  "gender": "male",
  "dob": "21/12/1995",
  "email": "pharshavardhan2@gmail.com",
  "languages": ["english", "telugu"],
  "programmingLanguages": ["js", "java", "python"],
  "Education": [
    {
      "level": "masters",
      "graduationYear": 2023,
      "college": "IISc, Bangalore",
      "specialization": "ECE"
    },
    {
      "level": "Bachelors",
      "graduationYear": 2016,
      "college": "JNTU college of engineering, Anantapur",
      "specialization": "ECE"
    }
  ],
  "Experience": [
    {
      "organization": "TCS",
      "duration": "2016-17",
      "designation": "Assistant System Engineer"
    },
    {
      "organization": "Unacademy",
      "duaration": "present",
      "designation": "Content reviewer"
    }
  ],
  "achievements": [
    {
      "exam": "IIT-JEE",
      "rank": 5315,
      "year": 2012
    },
    {
      "exam": "GATE-EC",
      "rank": 115,
      "year": 2021
    }
  ]
}
```
