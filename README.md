# nuxtPagination 

### 使用说明：
```js
<nuxt-Pagination :page-size="pageSize"
                     :current-page="current"
                     :total="total"
                     :type="type"
                     v-if="count > 1"></nuxt-Pagination>
```
### 参数说明：

1. pageSize------每页显示多少条（默认10条）
2. current-------当前页码（默认第1页）
3. total---------总条数
4. count---------共多少页

type----------对应query中的分类type


### 实现思路：

##### 1、总页数 count <= 11时
```js
[1,2,3,4,5,6,7,8,9,10,count]
```
##### 2、总页数 count > 11时
```js
# 如果当前页数 currentPage < = 6
  [1,2,3,4,5,6,7,8,9,10,...,count] --------------- 前边共10个
    
# 如果当前页数 currentPage > 6
#   如果当前页数 currentPage + 5 < count
    [1,...,3,4,5,6,7,8,9,10,11,...,13]  -------- 中间共9个，当前页前后各4个
#   如果当前页数 currentPage + 5 >= count
    [1,...,3,4,5,6,7,8,9,10,11,12] ------------- 最后共10个
```
