# array-span
Simple data structure to map objects onto array buffer

```
var spans = Span.page(length: 2, pages: 3); // [0, 1], [2, 3], [4, 5]
var array = [6, 7, 8, 9, 10, 11];
Span.get(array, spans[0], 1); // 7
Span.get(array, spans[2], 0); // 10

var obj = {
    _buffer: array,
    _span: Span.from(offset: 0, length: 2),
    x(): Span.get(_buffer, _span, 0),
    y(): Span.get(_buffer, _span, 1)
}

```
