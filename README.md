# Cabin
这是TOGAPhotos项目的用户页面代码仓库。

## 框架
本项目基于
- typescript@5.4.x
- vue@3.x
- pinia@2.x
- element-plus@2.x

## 组件拆分指南
- 当一个页面中存在一个逻辑复杂且相对独立的组件时，应该将其拆分成一个单独的组件
    - 相对独立：组件中没有或仅有一到两个属性需要与页面进行交互
    - 逻辑复杂：需要使用多个函数或对象方法才能完成处理
- 一个会在多处复用的功能也应该将其独立成组件

## Git协作流程
1. **fork**到自己到账号下
2. 从dev或者任何需要修改的feature分支上开一个新的分支
3. ...**Coding**...
4. 提交到自己仓库的feature分支上
5. 开一个PR，将代码合并到dev或者对应的feature分支
6. 等待合并

## 代码风格指南
总的来说，本项目的代码风格遵循**谷歌开源项目风格指南**。 以下提及的要求，为开发过程中必须遵守的内容，其余可视情况而定
 
1. 使用 `===`而非`==`！！！**这非常重要，任何情况下都不要使用`==`**。 
2. 命名
   1. 变量使用驼峰命名法
   2. 常量（包括类中的`readonly`）使用全大写字单词和单词直接用下划线连接`CONST_CASE`

3. 严禁使用`var`,在可能的情况下尽量使用`const`
4. 尽量利用TypeScript自己的类型推导系统
    ``` typescript
   //为userId标注类型对提高可读性并没有帮助
    let userId:number = 1
   //正确例子
    let photoId = 1;
    ```
   
5. 使用`interface`关键字而非`type`

    根据TypeScript团队负责人Daniel Rosenwasser的说法`type`关键字除了与`interface`显而易见的问题之外（无法声明合并和用于声明类）还有潜在的性能问题。
    > Honestly, my take is that it should really just be interfaces for anything that they can model. There is no benefit to type aliases when there are so many issues around display/perf. 
    >
    > We tried for a long time to paper over the distinction because of people’s personal choices, but ultimately unless we actually simplify the types internally (could happen) they’re not really the same, and interfaces behave better.
   
