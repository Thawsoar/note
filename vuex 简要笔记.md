#  vuex 简要笔记

#### 目录结构

<img src="https://cdn.jsdelivr.net/gh/Thawsoar/FigureBed@master//img/20200416120150.png"  />

#### state

> state 访问状态对象， 类似于data

1. 通过computed的计算属性直接赋值

```js
computed:{

  count(){
   return this.$store.state.count;
  }

}
```

![build:started](https://www.travis-ci.org/Thawsoar/happyfly-info.svg?branch=master&status=started)

2. 通过mapState的对象来赋值

```js
import {mapState} from 'vuex';

computed: mapState({

	count:state=>state.count

})

// 或

computed: {

  ... mapState({

  	count:state=>state.count

	})

// modules下

	...mapState('app', {

		name: state => state.name

	})
}
```



3. 通过mapState的数组来赋值

> 传字符串参数 'count' 等同于 `state => state.count`

> 当映射的计算属性的名称与 state 的子节点名称相同时才生效

```js
import {mapState} from 'vuex';

computed: {

  ...mapState(["count"]),

  // modules下

  ...mapState('user', [

  	'name'

  ])
}
```



***

#### gutter

> 在获取数据之前进行的一种再编辑,相当于对数据的一个过滤和加工。你可以把它看作store.js的计算属性 

```js
computed:{
	...mapState(["count"]),
	count(){
		return this.$store.getters.count;
	}
},
```

![](https://cdn.jsdelivr.net/gh/Thawsoar/FigureBed@master//img/20200416120235.png)

***



#### mutations

> 同步修改状态对象 相当于methods 同步方法

![](https://cdn.jsdelivr.net/gh/Thawsoar/FigureBed@master//img/QQ20200416-122934@2x.png)

1. 可以通过commit方法来修改状态

```js
this.$store.commit('add', '1')

```

2. 通过mapMutations来引入mutations

```js


import { mapState,mapMutations } from 'vuex';

methods: {
	...mapMutations([
		'add','reduce'
	]),

  ...mapMutations({
    add: 'add'
  }),
    
  // modules下
  ...mapMutations('app', [
  	'add'
  ]),
}

// 或
methods: mapMutations({

  mapMutations([
  	'add','reduce'
  ]})
}
```



***

#### actions

> 异步修改状态对象

> 在store.js中声明actions actions是可以调用Mutations里的方法的

1. 通过dispatch分发

```js
this.$store.dispatch('increment')

// 以载荷形式分发
store.dispatch('incrementAsync', {
	amount: 10
})

// 以对象形式分发
store.dispatch({
	type: 'incrementAsync',
	amount: 10
})
```



2. 通过mapActions 引入actions

```js
import { mapActions } from 'vuex';

methods:{

	...mapActions(['addAction','reduceAction'])

},
```