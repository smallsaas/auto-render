## 路由项子项标准组件

| 子类型名称            | 子类型说明                                        | 所有属性                                            |
| ---------------- | ---------------------------------------------------- | --------------------------------------------------- |
| MagicItem        | 一个图标在上，标题在下的路由导航栏                      | `[img,color,title,nav,container,size]`              |
| CardItem         | 一个图标在左，标题再右的路由导航栏                      | `[img,color,title,nav,container,size]`              |
| SubtitleCardItem | 同`CardItem`, 有副标题属性的路由导航栏                 | `[img,color,title,subtitle,nav,container,size]`     |
| RowItem          | 一个图标在左侧, 紧靠标题, 右侧是箭头                    | `[img,color,title,nav,group,container,size]`  |
| BoxItem          | 统计数字在上，标题在下的统计项，无路由属性, 有数据值格式  | `[number,title,format,container,size]`              |


## 列表项子项组件
> 页面复合组件

| 组件名              | 组件                              | 组件参数说明                                                        |
| ------------------ | --------------------------------- | ------------------------------------------------------------------ |
| SubjectItem        | 通用主题组件[标题,副标题,图片,标签,] | `[avatar/icon/url, title, subtitle, count, tag, tags[], status, size]`  |
| FeedSubjectCard    | 通用文章主题组件                    | `[url, images[], title, subtitle,align:[top,left,right,bottom], subject:[avatar, title], view,timestamp ]`


### `SubjectItem` 的参数说明
| 参数         | 组件参数说明                                        |
| ------------ | -------------------------------------------------- |
| avatar       | 头像`url`, 没有 [`url`,`icon`] 的话, 显示为圆形头像  |
| icon         | 图标`url`, 大小为 `24rpx`, 没有背景, 没有圆角        |
| url          | 图片`url`, 设置默认圆角                             |
| title        | 标题, 由全局 theme 决定                             |
| subtitle     | 副标题, 由全局 theme 决定                           |
| count        | 用于在标题右则显示数量                               |
| tag          | 标题右侧标签                                        |
| tags         | 副标题下面标签集合                                  |
| status       | 组件右侧状态信息                                    |
| size         | 组件大小[medium,large], 默认为`medium`, `large` 尺寸可用于动态页面  |


### `FeedSubjectCard` 的参数说明
| 参数         | 组件参数说明                                        |
| ------------ | -------------------------------------------------- |
| url          | 大图片链接                                          |
| images       | 图片列表, 可以放三个并排图片                         |
| title        | 标题, 由全局 theme 决定                             |
| subtitle     | 副标题, 由全局 theme 决定                           |
| align        | 图片的对齐方式 `[left,right,top,bottom]`            |
| subject      | 主题[用户, 供应商]                                  |
| view         | 查看次数                                           |
| timestamp    | 时间                                               |


## 动态页面组件
> 页面复合组件

| 组件名             | 组件                            | 组件参数说明                                           |
| ------------------ | ------------------------------- | ---------------------------------------------------- |

