# Adding-Up-Times-with-Reduce
初始文件提供了无序列表，每个列表都有data-time属性，用分:秒表示了时间，要求把时间都加在一起，并用时：分：秒表示
效果：https://xl-z4869.github.io/Adding-Up-Times-with-Reduce/
### 一、知识点
#### 1.Array.map
在使用数组的原生API的时候需要注意伪数组的存在，需要用Array.from将其转化成数组
#### 2.Array.splite()
用来分割字符串，原列表中，根据分秒之间的：来进行分割
#### 3.Array.reduce()
用来进行元素的相加的运算
### 二、主要步骤
#### 1.首先获得要操作的元素
```
 const lis = Array.from(document.querySelectorAll('li'))
```
#### 2.获得总时间秒
首先要获得每个li里面的时间
再将每个时间根据:分离，并转成数字 
将分转成秒
将每个事件的秒进行相加，得到总的事件秒
```
const seconds = lis
    .map(time => time.dataset.time)
    .map(timeCode => {
        const [min, sec] = timeCode.split(':').map(parseFloat)
        return (min * 60) + sec;
    })
    .reduce((total, sec) => total + sec);
```
#### 3.将总时间秒转化为时，分，秒
```
const hour = Math.floor(seconds
const min = Math.floor(seconds 
const sec = Math.floor(min % 60
console.log(hour, min, sec);
```
