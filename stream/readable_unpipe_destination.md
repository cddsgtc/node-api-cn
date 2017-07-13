<!-- YAML
added: v0.9.4
-->

* `destination` {stream.Writable} 操作一个明确的流（可写）为unpipe

 `readable.unpipe()` 方法会检测原先已经使用[`stream.pipe()`][]方法的一个可写流。

如果 `destination` 是没有指定过的，那么会检测所有的pipe。

如果 `destination` 是制定过的，但是其没有使用过pipe，那么该方法什么也不做。

```js
const readable = getReadableStreamSomehow();
const writable = fs.createWriteStream('file.txt');
// All the data from readable goes into 'file.txt',
// but only for the first second
readable.pipe(writable);
setTimeout(() => {
  console.log('Stop writing to file.txt');
  readable.unpipe(writable);
  console.log('Manually close the file stream');
  writable.end();
}, 1000);
```

