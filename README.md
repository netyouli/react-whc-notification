# react-whc-notification
A react、vue、react native module to post and observer notification, it works on React 、React-Native 、Vue、H5. (支持一对多发送通知消息、主要解决react、react-native、vue、h5夸组件页面之间的通信状态管理等)

### 该组件可以用来替代Redux，Vuex进行状态管理，使用更加简单高效，强力推荐

[ ![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-brightgreen.svg)](https://github.com/netyouli/react-whc-notification/pulls)
[ ![NPM version](http://img.shields.io/npm/v/react-whc-notification.svg?style=flat)](https://www.npmjs.com/package/react-whc-notification)
[![License MIT](http://img.shields.io/badge/license-MIT-orange.svg?style=flat)](https://raw.githubusercontent.com/crazycodeboy/react-whc-notification/master/LICENSE)


## Content

- [Installation](#installation)
- [Getting started](#getting-started)
- [API](#api)
- [Contribution](#contribution)

## Installation

* 1.Run `npm i react-whc-notification --save`
* 2.`import Notification from 'react-whc-notification'`

## Getting started  

Add `react-whc-notification` to your js file.

`import Notification from 'react-whc-notification'`

Add observer notification:

```javascript
 constructor(props) {
      super(props);
      Notification.addObserver(this, 'ObserverNotificationName' ,(param) => {
          console.log(param);
      });

      // 最后一个参数true用来补发通知（主要是用于监听已经发过的通知但是监听者还没来得及注册监听的情况）
      Notification.addObserver(this, 'ObserverNotificationName' ,(param) => {
          console.log(param);
      }, true);
  }

```

Post notification:

```javascript
Notification.post('ObserverNotificationName', '通知传递的参数可以是任意数据类型');
```

Remove specified observer notification:

```javascript
componentWillUnmount() {
    Notification.removeObserver(this, 'ObserverNotificationName');
}

```

Remove all observer notification:

```javascript
componentWillUnmount() {
    Notification.removeObserver(this);
}

```

## API


Method   |  Type     | Optional | Description
----------------- | -------- | -------- | -----------
post(string, any)   | function | true | post notification
addObserver(object, string, function, boolean)  |   function  |  true   | observer notification
removeObserver(object, string)  |   function  |  true   | remove observer notification


## Contribution

Issues are welcome. Please add a screenshot of bug and code snippet. Quickest way to solve issue is to reproduce it on one of the examples.

Pull requests are welcome. If you want to change API or making something big better to create issue and discuss it first.

---

**MIT Licensed**
