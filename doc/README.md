# Tapas Server

## Read

```
// EntryPoints/Usersjs
export const entity = 'users'
export const read (id, attributes, with, next) {}

// index.js
import Users from '../EntryPoints/Users'
tapas.entryPoint(Users)

tapas.listen()
```

```
// EntryPoints/Users.js
export const entity = {users: {friends: 'users'}}
export const read (id, attributes, with, next) {}

// index.js
import Users from '../EntryPoints/Users'
tapas.entryPoint(Users)

tapas.listen()
```

```
// EntryPoints/Users.js
export const entity = {users: {cats: 'users'}}
export const read (id, attributes, with, next) {}

// EntryPoints/Cats.js
export const entity = 'cats'
export const read (id, attributes, with, next) {}

// index.js
import Users from '../EntryPoints/Users'
import Cats from '../EntryPoints/Cats'
tapas.entryPoint(Users)
tapas.entryPoint(Cats)

tapas.listen()
```

```
// EntryPoints/Articles.js
export const entity = {articles: {comments: 'comments'}}
export const read (id, attributes, with, next) {}

// EntryPoints/Comments.js
export const entity = {comments: {article: 'articles'}}
export const read (id, attributes, with, next) {}

// index.js
import Articles from '../EntryPoints/Articles'
import Comments from '../EntryPoints/Comments'

tapas.entryPoint(Articles, Comments)

tapas.listen()
```

```
let tapas = new require('tapas')('websocket', {port: 8080})
tapas.listen()
```

```
// EntryPoints/Users.js
export const entity = 'users'
export const read (id, attributes, with, next) {}
export const subscribe (id, attributes, with, next) {}
export const write (id, attributes, with, next) {}

// index.js
import Users from '../EntryPoints/Users'
tapas.entryPoint(Users)

tapas.listen()
```
