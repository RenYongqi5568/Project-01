**![logo](https://file.xdclass.net/note/2020/javaweb/%E5%9B%BE%E7%89%87/logo.png)愿景："让编程不再难学，让技术与生活更加有趣"  **

**更多课程请访问 xdclass.net**

### 第一章 ECMAScript6从入门到进阶完全指南课程简介

#### 第1集 ES6从入门到进阶完全指南

**简介：ES6从入门到进阶完全指南**

* 课程学习要求
  * 具备一定的web前端开发基础，有HTML/CSS/Javascript基础知识



* 学后水平
  * Javascript代码更加简洁规范
  * Javascript代码功能更加强大
  * 大大提升开发效率
  * 增加Javascript代码安全
    * 变量必须先声明再使用
    * 对不可扩展对象添加属性会抛出异常
    * 在严格模式中，函数的参数必须是唯一的（不允许有重复的）
  * 前端开发职位要求
  * js框架（vue、react）开发应用



* 学习形式
  * 视频讲解 + 文字笔记 + 代码分析 + 交互流程图

  * 配套源码 + 笔记 + 课程软件 + 技术交流群 + 答疑



​                      <img src="./img/image-20211130200002390.png" alt="image-20211130200002390" style="zoom:67%;" />                                         <img src="img/image-20211111154743614.png" alt="image-20211111154743614" style="zoom:50%;" />  









#### 第2集 ECMAScript6课程大纲速览

**简介：ECMAScript6课程大纲速览**

- 大纲速览















![logo](https://file.xdclass.net/note/2020/javaweb/%E5%9B%BE%E7%89%87/logo.png)**愿景："让编程不再难学，让技术与生活更加有趣"  **

**更多课程请访问 xdclass.net**

### 第二章 ECMAScript6简介及项目环境搭建

#### 第1集 ECMAScript 6简介

**简介： 介绍ECMAScript 和 JavaScript以及ECMAScript 2015 的关系**

* ECMAScript 6是什么

  ECMAScript 6.0（以下简称 ES6）是 JavaScript 语言的下一代标准，已经在2015年6月正式发布了。它的目标，是使得 JavaScript 语言可以用来编写复杂的大型应用程序，成为企业级开发语言。

  

* ECMAScript 和 JavaScript 的关系

  ECMAScript是JavaScript的标准，JavaScript是ECMAScript的实现。换句话说，如果说JavaScript是一门语言的话，那么ECMAScript就是这门语言遵循的语法书。

  

* ES6 与 ECMAScript 2015 的关系

  2011年的时候，ECMAScript 5.1版本发布，ECMA组织就开始准备6.0版本了。但因为这个版本引入的语法功能太多了，所以不可能通过一个版本就将所有功能涵盖。所以，标准委员会决定，标准在每年的6月份正式发布一次，作为当年的正式版本。接下来的时间，就在这个版本的基础上做改动，直到下一年的6月份，草案就自然变成了新一年的版本。这样一来，就不需要以前的版本号了，只要用年份标记就可以了。

  就这样ES6的第一个版本就在2015.6正式发布了，正式名称就是《ECMAScript 2015标准》(简称ES2015)

  

* 总结

  因此，ES6 既是一个历史名词，也是一个泛指，含义是5.1版以后的 JavaScript 的下一代标准，涵盖了ES2015、ES2016、ES2017等等，而ES2015 则是正式名称，特指该年发布的正式版本的语言标准

















#### 第2集 使用babel工具搭建ES6项目环境

**简介：讲解如何使用babel搭建ES6项目环境及babel的常用配置及用法**

- 为什么要使用babel工具
  - 采用 ECMAScript 2015+ 语法编写的代码转换为向后兼容的 JavaScript 语法，以便能够运行在当前和旧版本的浏览器或其他环境中

* node安装

  * http://nodejs.cn/download/

* 初始化工程项目

  ```js
  // 使用默认配置初始化项目
  npm init -y
  ```

* 安装对应的依赖包

  ```js
  // 本地安装babel-cli及对应的转化规则
  npm install --save-dev babel-cli babel-preset-es2015
  
  // 阿里巴巴定制的镜像源
  npm install -g cnpm --registry=https://registry.npm.taobao.org
  ```

* 创建项目目录

  * src目录用于存放编写的es6代码
  * dist目录用于存放由es6转化后的代码

* 配置babel

  * 新建`.babelrc`文件

    ```javascript
    // 配置用于转化当前代码的规则集
    {
      "presets": ["es2015"]
    }
    ```

  * babel的基本用法

    ```js
    // -o 参数指定输出文件
    node_modules/.bin/babel src/index.js -o dist/index.js
    
    // -d 参数指定输出目录
    node_modules/.bin/babel src -d dist
    ```
    
    
    
  *  配置package.json文件实时编译
  
    ```js
    // 配置启动脚本的命令
    "scripts": {
      // 监听index.js文件，一发生变化就执行babel转译的命令
      "dev": "babel src -w -d dist",
    }
    ```
    
    



















 **![logo](https://file.xdclass.net/note/2020/javaweb/%E5%9B%BE%E7%89%87/logo.png)愿景："让编程不再难学，让技术与生活更加有趣"  **

**更多课程请访问 xdclass.net**

### 第三章 全新的声明及数据赋值方式

#### 第1集 新的变量声明关键字let与const

**简介：详细讲解let与const关键词特点及使用的注意事项**

* 作用域

  * 全局作用域
  * 局部作用域
  * 块级作用域

* let

  * 用法：声明一个变量
  * 特点：
    * 只在声明的代码块内有效
    * 在同一作用域内不允许重复声明
    * 没有变量提升
    * 暂时性死区：在声明变量前，不能使用该变量

* const

  * 用法：声明一个只读的变量(可理解为常量)

  * 特点：同let命令

  * 注意事项：

    * 变量声明的同时必须立即赋值
    * 如声明的是简单类型的数据，变量的值不可改变

    




#### 第2集 探秘JS的第七种类型数据Symbol

**简介：介绍Symbol是什么及使用场景**

* 学习ES6之前JavaScript的数据类型

  * 原始类型数据
    * Number(数字)
    * String(字符串)
    * Boolean(布尔值)
    * Null(空对象指针)
    * Undefined(声明的变量未被初始化时)
    * **Symbol（独一无二的值）**
  * 复杂类型数据
    * Object(对象)

* 引入的背景

  * 对象的属性名容易产生命名冲突，为保证键名的唯一性，故es6引入Symbol这种新的原始类型数据，确保创建的每个变量都是独一无二的

* 特点

  * Symbol类型的数据是类似字符串的数据类型

    由于Symbol函数返回的值是原始类型的数据，不是对象，故Symbol函数前不能使用new命令，否则会报错

    ```js
    let xd = Symbol()
    typeof xd // Symbol
    ```

  * 创建独一无二的值

    ```js
    let xd1 = Symbol()
    let xd2 = Symbol()
    console.log(xd1===xd2) //false
    
    let xd1 = Symbol('小滴课堂')
    let xd2 = Symbol('小滴课堂')
    console.log(xd1===xd2) //false
    ```

* 用法

  - 定义对象的唯一属性名

    ```javascript
    // 在对象里用Symbol作为属性名的三种写法
    let xd = Symbol()
    
    // 第一种方式: 借助数组读取xd变量，此时不能用点运算符,点运算符默认后面的参数是字符串
    let a = {}
    a[xd] = '小滴课堂'
    
    // 第二种方式: 构造时声明
    let a = {
      [xd]: '小滴课堂'
    }
    
    // 第三种 Object.defineProperty
    let a = {}
    Object.defineProperty(a, xd, { value: '小滴课堂' });
    ```

  - 定义常量

    ```javascript
    // 定义字符串常量
    const xd = Symbol("小滴课堂");
    ```

    















#### 第3集 不可不知的解构赋值

**简介：深入原理讲解解构赋值及其常见用法**

* 介绍

  解构赋值可以理解为赋值操作的语法糖，它是针对数组或者对象进行模式匹配，然后对其中的变量进行赋值。代码书写上言简意赅，语义明确，也方便了对象数组的读取操作。
  
* 实质

  - ES6中只要某种数据可以循环迭代，都可以进行解构赋值。

* 使用场景

  * 数组解构

    ```js
    // 变量多时
    let [a, b, c] = [1, 2]
    console.log(a, b, c)	//1,2,undefined
    
    // 变量默认值
    let [a, b, c = 6] = [1, 2]
    console.log(a, b, c)	//1,2,6
    
    // 分割数组
    let [a, ...other] = [1, 2, 3]
    console.log(a, other)	//1,[2,3]
    
    // 空内容
    let [a,,b] = [1, 2, 3]
    console.log(a, b)	//1,3
    
    ```

  * 对象解构

    ```js
    // 使用
    let { a, b } = { a: 1, b: 2 };
    console.log(a, b);// 1,2
    
    // 重命名
    let { a: aa, b: bb } = { a: 1, b: 2 };
    console.log(aa, bb);// 1,2
    ```

  - 读取接口返回的数据

    ```js
    function xd() {
      return {
        name: '小滴课堂',
        wangzhi: [
          {
            url: 'xdclass.net',
          },
        ],
      };
    }
    
    let { name , wangzhi: [{ url }],} = xd();
    
    console.log(name, url); // 小滴课堂 xdclass.net
    ```

    













 **![logo](https://file.xdclass.net/note/2020/javaweb/%E5%9B%BE%E7%89%87/logo.png)愿景："让编程不再难学，让技术与生活更加有趣"  **

**更多课程请访问 xdclass.net**

### 第四章 玩转ES6新增的数据操作方法

#### 第1集 字符串的扩展方法及模板字符串

**简介：介绍ES6提供的新的字符串方法及模板字符串**


* 扩展的API

  | 方法                      | 描述                                                         |
  | ------------------------- | ------------------------------------------------------------ |
  | includes(string, index)   | 判断字符串中是否包含指定字符串，返回值是布尔值               |
  | startsWith(string, index) | 判断字符串的开头是否包含指定字符串，返回值是布尔值           |
  | endsWith(string, index)   | 判断字符串的尾部是否包含指定字符串，返回值是布尔值           |
  | repeat(n)                 | repeat() 方法返回一个新字符串，表示将原字符串重复n 次。      |
  |                           |                                                              |
  | 字符串补全                | 第一个参数是补全后的字符串长度，第二个参数是用于补全的字符串 |
  | padStart(length, str)     | 用于头部补全                                                 |
  | padEnd(length, str)       | 用于尾部补全                                                 |

* 模板字符串

  ```js
  // 语法
  const name = "张三"
  const age = 18
  const hobbies = "打篮球"
  
  // ES5写法
  const str1 = '我的名字是'+name+'，我今年'+age+'岁，我喜欢'+hobbies
  console.log(str1)
  
  // ES6写法
  const str2 = `我的名字是${name}，我今年${age}岁，我喜欢${hobbies}`
  console.log(str2)
  ```

* 使用模板字符串的注意事项
  * 使用模板字符串表示多行字符串时，所有的空格和缩进都会被保留在输出之中
  * 模板字符串中引入变量，要用 ${变量名} 这样的形式引入才可以
  * 模板字符串中的${.......} 大括号内部可以放入任意的 JavaScript 表达式，可以进行运算、可以引用对象属性、可以调用函数、可以甚至还能嵌套，甚至还能调用自己本身















#### 第2集 ES6扩展运算符的使用和数组的扩展方法

**简介：介绍ES6扩展运算符的使用和数组的扩展方法**

* 扩展运算符的使用

  * 深拷贝一维数组

    ```js
    const list = [1, 2, 3, 4, 5];
    const list1 = [...list];
    console.log(list1);
    ```

  * 分割数组

    ```js
    const list = [1, 2, 3, 4, 5];
    const [, ...list1] = list;
    console.log(list1);
    ```

  * 将数组转化成参数传递给函数       

    ```js
    const list = [1, 2];
    function xd(a, b) {
      console.log(a + b);
    }
    xd(...list);
    ```

* 新增的常用方法

  * fill（会改变原数组）
  
    ```js
    const list = [1, 2, 3, 4, 5];
    const list1 = [...list].fill(6);
    const list2 = [...list].fill(6, 1, 4);
    console.log(list1);
    console.log(list2);
    ```
  
  * find/findIndex
  
    ```js
    const list = [
      { hobby: '吃饭', id: 1 },
      { hobby: '睡觉', id: 1 },
      { hobby: '敲代码', id: 1 },
      { hobby: '吃饭', id: 2 },
    ];
    let str = '';
    for (let i = 0; i < list.length; i++) {
      if (list[i].hobby === '吃饭') {
        str = list[i];
      }
    }
    console.log(str);
    
    const result = list.find(function (item) {
      return item.hobby === '吃饭';
    });
    const result1 = list.findIndex(function (item) {
      return item.hobby === '吃饭';
    });
    console.log(result, result1);
    ```
  
  * flat
  
    ```js
    const list = [1, 2, 3, ['2nd', 5, 6, ['3rd', 7, 8]]];
    const list1 = [].concat(...list);
    console.log(list1);
    const list2 = list.flat(2);
    console.log(list2);
    
    ```
  
  * filter（改变长度过滤，返回数组）
  
    ```js
    const list = [
      { hobby: '吃饭', id: 1 },
      { hobby: '睡觉', id: 1 },
      { hobby: '敲代码', id: 1 },
      { hobby: '吃饭', id: 2 },
    ];
    
    const result = list.filter(function (item) {
      return item.hobby === '吃饭';
    });
    console.log(result); // [{ hobby: '吃饭', id: 1 },{ hobby: '吃饭', id: 2 }]
    ```
  
    
  
  

























#### 第3集 ES6数组中map

**简介：详细介绍ES6中map**



* map（改变内容）

  ```js
  const list = [
    { hobby: '吃饭', id: 1 },
    { hobby: '睡觉', id: 1 },
    { hobby: '敲代码', id: 2 },
  ];
  const list1 = list.map(function (i) {
    // return {
    //   action: i.hobby,
    //   state: i.id === 1 ? '喜欢' : '沉迷',
    // };
    let obj = {};
    Object.assign(obj, i);
    obj.state = i.id === 1 ? '喜欢' : '沉迷';
    return obj;
  });
  console.log(list);
  console.log(list1);
  
  ```

  













#### 第4集 ES6对象的新特性及新增方法

**简介：介绍ES6提供的新的特性及对象方法**

* 扩展运算符的使用
  * 深拷贝简单对象
  
    ```js
    const a = {
      aa: 1,
      bb: 2,
      cc: {
        dd: 1,
      },
    };
    const b = { ...a };
    a.aa = '1';
    a.cc.dd = '4';
    console.log(b);
    ```
  
  * 给对象设置默认值
  
    ```js
    const a = {
      aa: 1,
      bb: 2,
    };
    const b = { ...a, aa: '1' };
    console.log(b);
    ```
  
  * 合并对象
  
    ```js
    const a = {
      aa: 1,
      bb: 2,
    };
    const b = { cc: 3, dd: 4 };
    const c = { ...a, ...b };
    console.log(c);
    ```
  
    
  
* 属性初始化、方法的简写

  ```js
  const name = '张三';
  const age = 18;
  
  let obj = {
    name,
    age,
    sayHello() {
      console.log('hello');
    },
  };
  obj.sayHello();
  console.log(obj);
  ```

* 新增方法
  * Object.is
  
    ```js
    let res = Object.is(NaN, NaN);
    console.log(res, NaN === NaN);
    ```
  
  * Object.assign
  
    ```js
    let a = { aa: 1, bb: 2 };
    let b = { aa: '1' };
    let c = Object.assign(b, a);
    console.log(c);
    ```
  
  * Object.keys
  
    ```js
    let xd = {
      hobby1: '吃饭',
      hobby2: '睡觉',
      hobby3: '敲代码',
    };
    console.log(Object.keys(xd));
    ```
  
  * Object.values
  
    ```js
    let xd = {
      hobby1: '吃饭',
      hobby2: '睡觉',
      hobby3: '敲代码',
    };
    console.log(Object.keys(xd));
    ```
  
  * Object.entries
  
    ```js
    let xd = {
      hobby1: '吃饭',
      hobby2: '睡觉',
      hobby3: '敲代码',
    };
    console.log(Object.keys(xd));
    ```
  
    









































#### 第5集 Map与WeakMap对象的特点

**简介：详细介绍Map与WeakMap结构的特点**

* 背景

  JavaScript中的对象，实质就是键值对的集合，但是在对象里却只能用字符串作为键名。在一些特殊的场景里就满足不了我们的需求了，正因为此，Map这一数据提出了，它是JavaScript中的一种更完善Hash结构。

* Map对象

  * 用于保存键值对，任何值(对象或者原始值)都可以作为一个键名或一个值。

  * 使用介绍

    ```js
    // 通过构造函数创建一个Map
    let m = new Map();
    
    m.set([1,2],'张三')
    ```
  
* 内置API

  | 属性/方法       | 作用                                         | 例子              |
  | --------------- | -------------------------------------------- | ----------------- |
  | size            | 返回键值对的数量                             | m.size            |
  | clear()         | 清除所有键值对                               | m.clear()         |
  | has(key)        | 判断键值对中是否有指定的键名，返回值是布尔值 | m.has(key)        |
  | get(key)        | 获取指定键名的键值，如不存在则返回undefined  | m.get(key)        |
  | set(key, value) | 添加键值对，如键名已存在，则更新键值对       | m.set(key, value) |
  | delete(key)     | 删除指定键名的键值对                         | m.delete(key)     |

  * 遍历器生成函数
    * keys()
    * values()
    * entries()

* WeakMap

    * 只接受对象作为键名

        ```js
        const weakMap = new WeakMap([[{ name: 1 }, '张三']]);
        console.log(weakMap);
        ```

    - 无法遍历













#### 第6集 Set与WeakSet结构的特点

* 介绍

  Set是ES6给开发者提供的一种类似数组的数据结构，可以理解为值的集合。它和数组的最大的区别就在于: 它的值不会有重复项。

* 基本使用

  ```js
  // 创建
  let set = new Set();
  let set2 = new Set([1,2,3])
  
  // 添加元素
  set.add(1)
  
  ```

* 特点

  * 成员值唯一

* 属性及方法
    | 属性/方法     | 作用                                       | 例子          |
    | ------------- | ------------------------------------------ | ------------- |
    | size          | 返回成员个数                               | s.size        |
  | clear()       | 清除所有成员                               | s.clear()     |
  | has(value)    | 判断键值对中是否有指定的值，返回值是布尔值 | s.has(key)    |
  | delete(value) | 删除指定值                                 | s.delete(key) |
  
  ```js
  // 注意
  const a = { aa: 1 };
  const list = new Set([a]);
  console.log(list.has(a));
  
  
  key和value相等
  const list = new Set([1, 2, 3, 4]);
  console.log(list.keys());
  console.log(list.values());
  ```
  
* 用途

  ```js
  // 去重
  let arr = [1,2,2,3,4,4,4];
  let s = new Set(arr);
  //结果：Set {1,2,3,4}
  
  let newArr = Array.from(s);
  //结果：[1,2,3,4],完成去重
  ```

* WeakSet

  * 数组成员必须是对象
  * WeakSet结构也提供了add( ) 方法，delete( ) 方法，has( )方法给开发者使用，作用与用法跟Set结构完全一致。
  * WeakSet 结构不可遍历。因为它的成员都是对象的弱引用，随时被回收机制回收，成员消失。所以WeakSet 结构不会有keys( )，values( )，entries( )，forEach( )等方法和size属性。





























#### 第7集 Map、Set与Array及Object间的区别

**简介：详细介绍Map、Set与Array及Object间的区别**

* 增删改查

  ```js
  const a = { xd: '小滴课堂' };
  const list = [];
  const obj = {};
  const set = new Set();
  const map = new Map();
  
  //增加
  list.push(a);
  obj['xd'] = '小滴课堂';
  set.add(a);
  map.set('xd', '小滴课堂');
  console.log(list, obj, set, map);
  
  // 查询
  const resList = list.includes(a);
  const resobj = 'xd' in obj;
  const resSet = set.has(a);
  const resMap = map.has('xd');
  console.log(resList, resobj, resSet, resMap);
  
  //修改
  list.forEach(function (i) {
    i.xd = i.xd ? 'xdclass.net' : '';
  });
  obj.xd = 'xdclass.net';
  set.forEach(function (i) {
    i.xd = i.xd ? 'xdclass.net' : '';
  });
  map.set('xd', 'xdclass.net');
  console.log(list, obj, set, map);
  
  //删除
  const index = list.findIndex(function (i) {
    return i.xd === '小滴课堂';
  });
  list.splice(index, 1);
  delete obj.xd;
  set.delete(a);
  map.delete('xd');
  console.log(list, obj, set, map);
  ```

* 类型转换

  ```js
  // 对象转map
  const obj = { xd: '小滴课堂', website: 'xdclass.net' };
  const map = new Map(Object.entries(obj));
  console.log(map);
  // map转对象
  const obj1 = Object.fromEntries(map);
  console.log(obj1);
  
  // 数组转set
  const list = [1, 2, 3];
  const set = new Set(list);
  console.log(set);
  
  // set转数组
  const list1 = Array.from(set);
  console.log(list1);
  ```

  











































#### 第8集 ES6高阶知识点之代理Proxy和反射Reflect(上)

**简介：认识高阶知识点之代理Proxy和反射Reflect**

* Proxy

  * 概述

    正如Proxy的英译"代理"所示，Proxy是ES6为了操作对象引入的API。它不直接作用在对象上，而是作为一种媒介，如果需要操作对象的话，需要经过这个媒介的同意。

  * 使用方式

    ```js
    /* @params
    ** target: 用Proxy包装的目标对象
    ** handler: 一个对象，对代理对象进行拦截操作的函数，如set、get
    */
    let p = new Proxy(target, handler)
    ```

  * 使用场景

    ```js
    const house = {
      name: '张三',
      price: '1000',
      phone: '18823139921',
      id: '111',
      state: '**',
    };
    
    const houseProxy = new Proxy(house, {
      // 读取代理
      get: function (target, key) {
        switch (key) {
          case 'price':
            return target[key].replace('1000', '1200');
          case 'phone':
            return target[key].substring(0, 3) + '****' + target[key].substring(7);
          default:
            return target[key];
        }
      },
      // 设置代理
      set: function (target, key, value) {
        if (key === 'id') {
          return target[key];
        } else if (key === 'state') {
          return (target[key] = value);
        }
      },
    });
    
    console.log(houseProxy.price);
    console.log(houseProxy.phone);
    
    houseProxy.id = '222';
    houseProxy.state = '****';
    console.log(houseProxy.id);
    console.log(houseProxy.state);
    ```

    

* Reflect

  * 概述

    与Proxy相同，ES6引入Reflect也是用来操作对象的，它将对象里一些明显属于语言内部的方法移植到Reflect对象上，它对某些方法的返回结果进行了修改，使其更合理，更具语义化，并且使用函数的方式实现了Object的命令式操作

  * 常见用法

    ```js
    const person = {
      name: '张三',
      age: '18',
      phone: '18823139921',
      id: '111',
    };
    const res = 'name' in person;
    const res1 = Reflect.has(person, 'name');
    console.log(res, res1);
    ```

    


















#### 第9集 使用Proxy实现简单的双向数据绑定

**简介：手把手教你如何使用Proxy实现简单的双向数据绑定**

* 获取dom对象

  ```js
  const input = document.getElementById('input');
  const span = document.getElementById('span');
  ```

* 设置代理对象

  ```js
  const obj = {};
  const inputProxy = new Proxy(obj, handler);
  ```

* 配置代理选项

  ```js
  const handler = {
    get: function (target, key) {
      return target[key];
    },
    set: function (target, key, value) {
      if (key === 'text' && value) {
        span.innerHTML = value;
        return (target[key] = value);
      }
    },
  };
  ```

* 添加事件

  ```js
  input.addEventListener('keyup', function (e) {
    inputProxy.text = e.target.value;
    console.log(inputProxy.text);
  });
  ```









































 **![logo](https://file.xdclass.net/note/2020/javaweb/%E5%9B%BE%E7%89%87/logo.png)愿景："让编程不再难学，让技术与生活更加有趣"  **

**更多课程请访问 xdclass.net**

### 第五章 函数的扩展、类的概念及模块化

#### 第1集 函数参数的扩展

**简介：函数参数的扩展**

* 函数参数可设置默认值

  ```js
  function xd(a, b = 3) {
    console.log(a + b);
  }
  xd(1, '');
  ```

* rest参数

  ```js
  function xd(...rest) {
    console.log(rest);
  }
  xd(1, 2, 3);
  ```

* 扩展运算符

  ```js
  function xd(a, b, c) {
    console.log(a, b, c);
  }
  xd(...[1, 2, 3]);
  ```

  









































#### 第2集 深入浅出箭头函数

**简介：详细讲解箭头函数的使用及注意事项**

* 特点
  * 更短的函数
  
    ```
    ()=>{}
    ```
  
  * 不绑定this
  
    ```js
    const xd = {
      a: 1,
      sum() {
        setTimeout(() => {
          console.log(this.a);
        }, 1000);
      },
    };
    
    xd.sum();
    ```
* 注意事项
  * 什么情况下不能箭头函数
  
    - 定义对象的方法
  
      ```js
      const xd = {
        a: 1,
        sum: () => {
          console.log(this);
        },
      };
      xd.sum();
      ```
  
    - 定义DOM事件的回调函数
  
      ```js
      const h3 = document.getElementById('h3');
      h3.addEventListener('click', () => {
        this.innerHTML = 11;
      });
      ```
  
    - 定义构造函数
  
      ```js
      const Car = () => {
        console.log(this);
      };
      Car();
      ```
  
      
  
  * 箭头函数没有argument

























#### 第3集 ES6中全方位理解类的概念

**简介：详细讲解类的概念及如何实现类的封装及继承**

ES6之前javascript中只有对象，没有类的概念。它是基于原型的面向对象语言。原型对象特点就是将自身的属性共享给新对象。

<img src="img/WechatIMG16.png" alt="WechatIMG16" style="zoom:67%;" />

* new操作做了什么事

  * 返回（产生）了一个新的对象

  * 将这个空对象的_ proto_指向了构造函数内部的prototype

  * 将构造函数的this绑定到这个对象上(即new创建的对象，其函数体内的this指向的是这个对象)

  * 返回到这个新对象上

* es6 class的概念

  * 定义类
  
    ```js
    class Person1 {
      constructor(name, age) {
        this.name = name;
        this.age = age;
      }
      sayHello() {
        console.log(`我是${this.name},今年${this.age}岁`);
      }
    }
    
    const person1 = new Person1('张三', 18);
    
    person1.sayHello();
    console.log(person1);
    ```
  
  * 类的继承
  
    ```js
    class Parent {
      constructor(name, age) {
        this.name = name;
        this.age = age;
      }
      sayHello() {
        console.log(`我是${this.name},今年${this.age}岁`);
      }
    }
    
    class Student extends Parent {}
    
    const p = new Student('张三',18);
    console.log(p);
    ```
  
  * 子类复写父类的属性
  
    ```js
    class Student extends Parent {
      constructor(name, age, grade) {
        super(name, age);
        this.grade = grade;
      }
    }
    
    const p = new Student('张三', 18, '六年级')
    ```
  
  * 静态方法（不能被实例对象调用）
  
    ```js
    class Parent {
      constructor(name = '大钊') {
        this.name = name;
      }
      static say() {
        console.log(111);
      }
    }
    Parent.say();
    ```
  
  * 静态属性
  
    ```js
    class Parent {
      constructor(name = '大钊') {
        this.name = name;
      }
      static age = '18';
    }
    
    const p = new Parent();
    console.log(p.age);
    ```
  
    







#### 第4集 模块化开发(import和export)

**简介：介绍js的发展过程中如何实现模块化及import和export的使用**

* 背景：

  ES6之前是没有类的概念的，也就没有模块这一说法。理想情况下，开发者应该只注重核心业务的开发，对于其他有一定通用性的业务可以直接引入，也就是模块。多人开发，本应如此。

* 提出的方案

  * CommonJS 
    * Commonjs是作为Node中模块化规范以及原生模块面世的
  * AMD和RequireJs
    * [AMD](https://github.com/amdjs/amdjs-api/wiki/AMD)是"Asynchronous Module Definition"的缩写，意思就是"异步模块定义"。它采用异步方式加载模块，模块的加载不影响它后面语句的运行。所有依赖这个模块的语句，都定义在一个回调函数中，等到**所有依赖加载完成之后**（前置依赖），这个回调函数才会运行。
  * Import 和 export





















 **![logo](https://file.xdclass.net/note/2020/javaweb/%E5%9B%BE%E7%89%87/logo.png)愿景："让编程不再难学，让技术与生活更加有趣"  **

**更多课程请访问 xdclass.net**

### 第六章 深入解析JavaScript中的异步编程

#### 第1集  什么是异步编程及JavaScript的异步实现

**简介：介绍异步编程的概念及前期JavaScript实现异步编程的几种方法**

* 同步

  当一个"调用"发出时，在没有得到结果之前，这个"调用"就会阻塞后面代码的执行，得到结果的时候才会返回。换句话说，"调用者"要主动等待代码的执行结果，得到返回结果后，程序才会继续运行。

* 异步

  "调用"发出的时候，就直接返回了，对应的结果会通过状态、通知来告诉"调用者"。异步调用发出后，不会阻塞后面的代码。

* JavaScript中为什么要引入异步这个概念

  * JavaScript是单线程的
  * 同步代码会阻塞后面的代码
  * 异步不会阻塞程序的运行

* JavaScript中异步的实现

  * 回调函数

    ```js
    // 请求后端接口数据时，使用promise封装ajax的axios请求库
    axios.get('a.json').then((res) => {
      if (res && res.data.code === 0) {
        console.log(res.data.data.data);
      }
    });
    ```
    
  * setInterval和setTimeout
  
  * Promise
  
  * Generator
  
  * async









































#### 第2集 解决回调地狱提出的新方案—Promise

**简介：深入讲解Promise的概念及其原理**

背景：为了解决"回调地狱"的问题，提出了Promise对象

- 回调地狱（为了实现接口请求按照一定顺序执行出现）

  - 可读性差，后期不好维护

  - 代码耦合

  - 出错时，无法排除

    ```js
    function request() {
      axios.get('a.json').then((res) => {
        if (res && res.data.code === 0) {
          console.log(res.data.data.data);
          axios.get('b.json').then((res) => {
            if (res && res.data.code === 0) {
              console.log(res.data.data.data);
              axios.get('c.json').then((res) => {
                console.log(res.data.data.data);
              });
            }
          });
        }
      });
    }
    
    request();
    ```

* Promise

  - 简单说就是一个容器，里面保存着某个未来才会结束的事件（通常是一个异步操作）的结果。
  - 从语法上说，Promise 是一个对象，从它可以获取异步操作的的最终状态(成功或失败)。
  - Promise 是一个构造函数，提供统一的 API，Promise里不仅可以存放着异步的代码，也可以放同步的代码。

  ```js
  // 准备阶段
  new Promise((resolve, reject) => {})
  
  // 成功状态
  new Promise((resolve, reject) => {
    resolve('成功'); // 同步代码
  }).then((res) => {
    console.log(res);
  });
  
  // 失败状态
  new Promise((resolve, reject) => {
    reject('失败');
  }).catch((err) => {
    console.log(err);
  });
  ```

* 特点

  - Promise对象的状态不受外界影响

    - pending 初始状态

    - resolve 成功状态

    - rejected 失败状态

      Promise 有以上三种状态，只有异步操作的结果可以决定当前是哪一种状态，其他任何操作都无法改变这个状态

  - Promise的状态一旦改变，就不会再变，任何时候都可以得到这个结果，状态不可以逆，只能由 pending变成resolve或者由pending变成rejected

* Promise解决回调地狱

  ```js
  function requestA() {
    return new Promise((resolve, reject) => {
      axios.get('a.json').then((res) => {
        resolve(res);
      });
    });
  }
  
  function requestB() {
    return new Promise((resolve, reject) => {
      axios.get('b.json').then((res) => {
        resolve(res);
      });
    });
  }
  
  function requestC() {
    return new Promise((resolve, reject) => {
      axios.get('c.json').then((res) => {
        resolve(res);
      });
    });
  }
  
  
  function request() {
    requestA()
      .then((res) => {
        console.log(res);
        return requestB();
      })
      .then((res) => {
        console.log(res);
        return requestC();
      })
      .then((res) => {
        console.log(res);
      })
  }
  
  request();
  ```

* Promise.all方法

  - Promise.all 实际上是一个函数，它接受一个 `promise` 数组并返回一个 `promise`。然后当所有的 `promise` 都完成时会得到结果数组或者当其中一个被拒绝时会抛出错误
  - 返回值将会按照参数内的 `promise` 顺序排列，而不是由调用 `promise` 的完成顺序决定。

  ```js
  function requestAll() {
    Promise.all([requestA(), requestB(), requestC()])
      .then((res) => {
        console.log(res);
      })
      .catch((err) => {
        console.log(err);
      });
  }
  
  requestAll();
  ```

* Promise.race

  Promse.race就是赛跑的意思，传入的`promise` 数组里面哪个结果获得的快，就返回那个结果，不管结果本身是成功状态还是失败状态。
  
  ```js
  function requestRace() {
    Promise.race([requestA(), requestB(), requestC()])
      .then((res) => {
        console.log(res);
      })
      .catch((err) => {
        console.log(err);
      });
  }
  
  requestRace();
  ```
  
  



#### 第3集 优雅的异步编程—async

**简介：介绍async函数的语法及使用的注意事项** 

* 什么是async

  async是异步的简写，Generator（生成器）的语法糖，用于声明一个函数是异步函数

  ```js
  async function xd() {
    await console.log('小滴课堂');
  }
  xd();
  ```

* 优点

  * 内置执行器
  * 更好的语义
  * 更广的适用性
  
* async await改造promise.then异步调用

  ```js
  function requestA() {
    return new Promise((resolve, reject) => {
      axios.get('a.json').then((res) => {
        setTimeout(() => {
          resolve(res);
          console.log('aaa');
        }, 1000);
      });
    });
  }
  
  function requestB() {
    return new Promise((resolve, reject) => {
      axios.get('b.json').then((res) => {
        setTimeout(() => {
          resolve(res);
          console.log('bbb');
        }, 1000);
      });
    });
  }
  
  function requestC() {
    return new Promise((resolve, reject) => {
      axios.get('c.json').then((res) => {
        setTimeout(() => {
          resolve(res);
          console.log('ccc');
        }, 1000);
      });
    });
  }
  async function request() {
    try {
      const a = await requestA();
      const b = await requestB();
      const c = await requestC();
      console.log(a, b, c);
    } catch (err) {
      console.log(err);
    }
  }
  
  request();
  ```
  
  















 **![logo](https://file.xdclass.net/note/2020/javaweb/%E5%9B%BE%E7%89%87/logo.png)愿景："让编程不再难学，让技术与生活更加有趣"  **

**更多课程请访问 xdclass.net**

### 第七章 课程总结及面试常考点

#### 第1集 课程总结及面试常考点

**简介： 课程总结及面试常考点**

* 开发中常用到的知识

  * 解构赋值
    * 对象的解构
    * 数组的解构
  * set、map方法
  * 箭头函数
  * Promise函数
    * 结合async函数，异步编程同步化

- 作用域
- 简单深拷贝实现方法
  - ...
  - Object.assign()

* 数组操作方法
* promise















