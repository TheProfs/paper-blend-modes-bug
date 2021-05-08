# paper-blend-modes-bug
PaperJS blend mode issue on large layers

## Run

```bash
$ npm install
$ npm start
```

## How it breaks.

- Create a `Layer`.
- Create another `Layer`.
- Set the `blendMode` of the 2nd layer as anything other than normal.
- Draw a shape on layer 2.
- Scroll layer 2 view by `0, 8000`.
- Draw another shape.
- Scroll layer 2 view by `8000, 0`.
- Draw another shape.

## What happens:

Layer 2 doesn't render anything. This is because of the size of Layer 2.
If we scroll by a lesser value, say `0, 5000` and `5000, 0`, it renders OK
at least on Chrome 90.

On iOS 14 Safari it still doesn't render and also the following warning message
appears:

> Canvas area exceeds the maximum limit (width * height > 16777216).
https://paper-blend-modes-bug.herokuapp.com/favicon.ico


## Authors

Bitpaper LTD
