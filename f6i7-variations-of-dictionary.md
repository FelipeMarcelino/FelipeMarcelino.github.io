# Variations of Dictionary
#python #datastructure #programming #language

## Ordered Dict
Used to make the code compatible with old version of python. Maintain the keys sorted and use more memory for it.

## Chain Map
You can chain multiple dictionaries, it has a reference for each one of them. Can be used to create interpreter of
language simulating the scope for example. Updates and insertions happens only in the first/head dictionary.

## Counter
Count the occurrences of keys (hashables). Has the operations `+` and `-`.

## Shelf
Used as storage, but the keys need to be a string. They are saved using `pickle`.

## Mapping Proxy Type
They are maps that avoid changing the object after instantiate it because it is immutable. Your usage are common to map
hardware APIs because software cannot change hardware.

### References
- Ramalho, 2022, p83-96
- Ramalho, 2022, p97-100
