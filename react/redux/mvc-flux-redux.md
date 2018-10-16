# MVC & FLUX#



### MVC

#### 组成

1. 模板/HTML = View
2. 填充视图的数据 = Model
3. 获取数据，将所有视图组装在一起，用户事件数据变化时的响应，等等的逻辑 = Controller

#### 交互模式

1. 用户点击按钮“A”
2. 点击按钮“A”的处理程序触发 Model “A”的改变
3. Model “A”的改变处理程序触发 Model “B”的改变
4. Model “B”的改变处理程序触发 View “B”的改变并重新渲染自身



### FLUX

#### 组成

1. Model 看起来像 Store
2. 用户事件、数据变化以及它们的处理程序看起来像"action creators" -> action -> dispatcher -> callback
3. View 看起来像 React views (或者其他什么的)

#### 交互模式

1. 用户点击按钮“A”
2. 点击按钮“A”的处理程序会触发一个被分发的 action，并改变 Store “A”
3. 因为其它的 Store 也被这个 action 通知了，所以 Store “B”也会对相同的 action 做出反应
4. View “B”因为 Store  A 和 Store B的改变而收到通知，并重新渲染

# Redux

### 是什么？

1. 存放应用程序状态的容器
2. 一种把 action 分发到状态修改器的机制，也就是 reducer 函数
3. 监听状态变化的机制

```
import {createStore} from 'redux'
let reducer = function(...args) {
  console.log('Reducer was called with args', args)
}
let store = createStore(reducer) //store为Redux的实例
```



### Action

1. 返回值为普通的javascript对象``` {type : 'An_action', data : ''}```
2. 返回值为函数，处理异步action极为有用

#### 同步Action

```action ---> dispatcher ---> reducer ```

```
function actionCreator() {
  return {
  	type : 'Sync' //同步
  }
}
let syncAction = actionCreator();//return plain JavaScript objects
```



#### 异步Action

```action ---> dispatcher ---> middleware 1 ---> middleware 2 ---> reducers```

```
function asyncActionCreator() {
  setTimeout(function() {
  	return {
  		type : 'Async'//异步
	};
  }, 2000);
}
let asyncAction = asyncActionCreator();//return Function,reducer无法识别，保错！
```



#### Reducer

1. 是一个纯函数，接受当前状态及发生的action,返回新的状态（归并后的状态）
2. actions的订阅者
3. 简而言之，用来修改数据







