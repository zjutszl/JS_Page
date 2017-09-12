


# v-for

## 最简
<ul id="example-1">
  <li v-for="item in items">
    {{ item.message }}
  </li>
</ul>

var example1 = new Vue({
  el: '#example-1',
  data: {
    items: [
      { message: 'Foo' },
      { message: 'Bar' }
    ]
  }
})

## 第二个变量:Index为索引
<ul id="example-2">
  <li v-for="(item, index) in items">
    {{ parentMessage }} - {{ index }} - {{ item.message }}
  </li>
</ul>
var example2 = new Vue({
  el: '#example-2',
  data: {
    parentMessage: 'Parent',
    items: [
      { message: 'Foo' },
      { message: 'Bar' }
    ]
  }
})

## 得到object中的value，而不是variable

<ul id="v-for-object" class="demo">
  <li v-for="value in object">
    {{ value }}
  </li>
</ul>

## 两个变量:value,key
<div v-for="(value, key) in object">
  {{ key }}: {{ value }}
</div>

## 第三个参数为索引：
<div v-for="(value, key, index) in object">
  {{ index }}. {{ key }}: {{ value }}
</div>
0. firstName: John
1. lastName: Doe
2. age: 30
