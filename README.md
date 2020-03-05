# MPA front-end-architecture

## terms
### page
The view returned given a URL
### app shell
The consistent views and wrapping elements between pages
### content
The page specific elements of a give URL

**Thesis: Each `page` in a `MPA` is an `application`**

## Housing Structure
```js
Shared Application Dependencies___
|    Applications_______          |
|    |    App(Page)    |          |
|    |    App(Page)    |          |
|    |    App(Page)
|    |    App(Page)
|    |__________________
|
|_________________________________
```
