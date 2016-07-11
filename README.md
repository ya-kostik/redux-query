# redux-query

## Description
**It is not ready, it's just a some dreams about queries at redux**

Redux query make for control your redux data flow.

## Install
```
npm i redux-query
```
When action type starts from @@query, special reducer try to process it,
and apply only one, special for that query reducer.

For example, you can have reducer's tree like that:

* user `user reducer`
  *   profile `profile reducer`
    *     photos `photos reducer`
    *     bio `bio reducer`
  *   actions `actions reducer`
    *     news `news actions reducer`
    *     blog `blog actions reducer`
* document `document reducer`
* post `post reducer`

If you create your reducer's tree by standart `combineReducers` function, every
action will flow in every reducer

With redux-query you can control, what reducer will call for what action.
When you dispatch action with type `@@query/user/profile/bio/UPDATE`, redux-query
parse and call only `bio reducer`, with only user.profile.bio node as state.


The MIT License (MIT)

Copyright (c) 2016 Constantin Tsukanov

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
