<!-- YAML
added: v0.9.4
-->

* Returns: `this`

`readable.resume()`方法能够把一个明确paused状态的readable stream转换成flowing状态，并且恢复到可以发送`data`事件。

`readable.ruesume()`方法能够不需要处理任何数据，就可以完全消费一个流中的的数据，如下例子所示：

```js
getReadableStreamSomehow()
  .resume()
  .on('end', () => {
    console.log('Reached the end, but did not read anything.');
  });
```

