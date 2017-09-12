//以下大部分文字仅在Vue第三方库下成立。



* 为了给 Vue 一个提示，以便它能跟踪每个节点的身份，从而重用和重新排序现有元素，你需要为每项提供一个唯一 key 属性。理想的 key 值是每项都有的且唯一的 id。这个特殊的属性相当于 Vue 1.x 的 track-by ，但它的工作方式类似于一个属性，所以你需要用 v-bind 来绑定动态值（在这里使用简写）：

:key="item.id"  比 v-bind:key="item.id" 省略了v-bind，但效果一样。

修改数组长度时，不应该直接用（会无法检测到）：
```
//wrong
vm.items.length = newLength

//good
example1.items.splice(newLength)
```

Vue.set(vm.userProfile, 'age', 27)  ==> 可以给vm.userProfile新增一个'age':27

## 为已有对象赋予多个新属性
有时你可能需要为已有对象赋予多个新属性，比如使用 Object.assign() 或 _.extend()。在这种情况下，你应该用两个对象的属性创建一个新的对象。所以，如果你想添加新的响应式属性，不要像这样：
Object.assign(this.userProfile, {
  age: 27,
  favoriteColor: 'Vue Green'
})
你应该这样做：
this.userProfile = Object.assign({}, this.userProfile, {
  age: 27,
  favoriteColor: 'Vue Green'
})