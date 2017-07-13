<!-- YAML
added: v8.0.0
-->
Destroy 流，然后发出传递的错误事件。调用这个方法之后，writable流已经停止。
Implementors不应该覆盖这个方法，其自己相应的方法[`writable._destroy`][writable-_destroy]。
