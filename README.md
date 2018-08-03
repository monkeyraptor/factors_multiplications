# gfm.js
JavaScript function to get factors and multiples of a positive integer

## Usage
> `gfm(positive_integer_input)`

> Example: `gfm(81)`

## Input
> This function receives positive integer from `2` to `1,000,000,000` (1 billion).

> It only receives one argument (input).

## Output 
> For both **valid** and **invalid** inputs, the output will be an `object`.

> The outout `object` consists of:
```
{
    duration: "process in milliseconds",
    factors: [array of integers],
    multiples: [array of multiplication arrays]
}
```

## Examples
### VALID INPUT
> `gfm(81)` → input is `81` → **valid** input

> Output:

```
{
    duration: "0 ms",
    factors: [1, 3, 3, 3, 3],
    multiples: [[1, 81], [3, 27], [9, 9]]
}
```
### INVALID INPUT
> `gfm(-1.2)` → input is `-1.2` → **invalid** input

> Output:

```
{
    duration: "0 ms",
    factors: [],
    multiples: []
}
```
## About
This is sort of the continuation of <a href="https://github.com/monkeyraptor/getFactors.js">getFactors.js</a>.
