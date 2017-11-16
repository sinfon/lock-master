###### heiha

--------------------------------------------------------------

# Lock Master

--------------------------------------------------------------

关于 zk 锁的说明

```
 * 本方法内部所使用的 lock 是为设置对外锁，而使用的内部锁，不要混淆，外部锁是有 VALUE 且不可重入的
 * 
 * 想要做到可重入，在有锁存在的情况下，通过 get 方法获取 VALUE 来判断
 * 
 * 这种可重入的前提是，每个 VALUE 对应一个唯一的操作人，不存在同时操作的情况
 * 
 * 当前操作人，异常，未解锁就退出了，通过这种方式可重入并在操作完毕后解锁
 * 
 * 异常退出请务必不要解锁
 ```