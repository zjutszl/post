JS入门社群里有同学问到Vue生命周期怎么理解。

我就讲讲我的理解。欢迎批评指正！


---

Vue的生命周期图显示的是一个Vue的instance(实例)从创建到销毁的整个过程。

![img](https://vuejs.org/images/lifecycle.png)

图表中标红的事件有这么几个:

* beforeCreate
* created
* beforMount
* mounted
* beforeUpdate
* updated
* beforeDestroy
* destroy


这些事件是Vue实例的重要节点。

熟悉HTML的同学可能已经想到了：和HTML中的事件一样，这些Vue实例生命周期的事件也可以绑定function。

比如这样写Vue的实例：

```javascript
var vm = new Vue({
    el:'#app',
    data:{
        wordlist:[]
    },
    methods:{
        func:function(){//....}
    },
    beforeCreate:{
        function(){console.log("step 1");}
    },
    created:{
        function(){console.log("step 2");}
    },
    beforMount:{
        function(){console.log("step 3");}
    },
    mounted:{
        function(){console.log("step 4");}
    },
    beforeUpdate:{
        function(){console.log("step 5");}
    },
    updated:{
        function(){console.log("step 6");}
    },
    beforeDestroy:{
        function(){console.log("step 7");}
    },
    destroy:{
        function(){console.log("step 8");}
    }
})
```
当事件(比如说mounted)触发时，对应的function就会立即调用。

----

### 题外话：

el——与HTML的元素挂钩

data——实例中用到的数据

methods——可复用的function。不依靠事件触发，如有需要可以手动绑定。
