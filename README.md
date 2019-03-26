# nuxtPagination 使用说明

<nuxt-Pagination :page-size="pageSize"
                     :current-page="current"
                     :total="total"
                     :type="type"
                     v-if="count > 1"></nuxt-Pagination>

参数说明

pageSize------每页显示多少条（默认10条）
current-------当前页码（默认第1页）
total---------总条数
count---------共多少页

type----------对应query中的分类type
