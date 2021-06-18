# test
```
 https://getcomposer.org/
 https://packagist.org/
 
 https://github.com/
```

# composer之创建自己的包
```
    在github上创建一个项目（项目名称可以随意）
    编写composer.json
    copy代码文件并修改命名空间
    在https://packagist.org/上递交自己的包
    设置github的hook
    
    你可能需要在github上面发布几个release，这样packagist才会认定你的包是稳定的，否则只能required开发包。

设置github的hook
版本控制工具大多支持hook，用于代码递交时触发一个事件，将代码同步到其他环境中。
在github上设置hook后，我们每次pull，都会自动同步到packagist上，这样就不需要我们手动强制同步了。具体操作可以参见packgist的说明，操作很简单，耐心看下应该问题不大。

```
