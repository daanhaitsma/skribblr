# Skribblr
A ~~cheating~~ helper tool for Skribbl.io

## Creation of the word list
The word list is a modified version of https://github.com/skribbliohints/skribbliohints.github.io/blob/master/words.json

The list contains all words from the list linked above that contain uppercase characters. Since these are names, they might also show up in the Dutch version of Skribbl.

This was created using the following simple bit of JS:

```js
const results = Object.keys(/* copy/paste of json */)
    .filter(word => /[A-Z]/.test(word))
    .map(word => "'" + word + "',").join('<br>');

document.write(results);
```

This creates a nicely formatted list which can be copied straight into a javascript array.

```
'Vin Diesel',
'Daffy Duck',
'Batman',
'Patrick',
'Darwin',
'William Wallace',
...
```


## TODO
* Add ~~Dutch~~ Frysk words
* Watch the chat to remove any suggestions that have already been guessed by other players
* Upgrade the guesser to a backend or something with proper storage, so the word list can easily be expanded whenever a drawn word was not known yet
* If there is only one guess left, automatically submit that one
