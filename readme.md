# MONGO DB Practice

1. Insertar al menos 15 publicaciones nuevas con almenos 2 comentarios por publicación:

```
db.posts.insertMany([
{ title:"First post", body:"first post user1", username:"user1", comments:[
  {username:"user1", body:"comment1 user1 post1"},
  {username:"user1", body:"comment2 user1 post1"}]
},
{ title:"First post", body:"first post user1", username:"user2", comments:[
  {username:"user1", body:"comment1 user1 post1"},
  {username:"user1", body:"comment2 user1 post1"}]
},
{ title:"First post", body:"first post user1", username:"user3", comments:[
  {username:"user1", body:"comment1 user1 post1"},
  {username:"user1", body:"comment2 user1 post1"}]
},
{ title:"First post", body:"first post user1", username:"user4", comments:[
  {username:"user1", body:"comment1 user1 post1"},
  {username:"user1", body:"comment2 user1 post1"}]
},
{ title:"First post", body:"first post user1", username:"user5", comments:[
  {username:"user1", body:"comment1 user1 post1"},
  {username:"user1", body:"comment2 user1 post1"}]
},
{ title:"First post", body:"first post user1", username:"user6", comments:[
  {username:"user1", body:"comment1 user1 post1"},
  {username:"user1", body:"comment2 user1 post1"}]
},
{ title:"First post", body:"first post user1", username:"user7", comments:[
  {username:"user1", body:"comment1 user1 post1"},
  {username:"user1", body:"comment2 user1 post1"}]
},
{ title:"First post", body:"first post user1", username:"user8", comments:[
  {username:"user1", body:"comment1 user1 post1"},
  {username:"user1", body:"comment2 user1 post1"}]
},
{ title:"First post", body:"first post user1", username:"user9", comments:[
  {username:"user1", body:"comment1 user1 post1"},
  {username:"user1", body:"comment2 user1 post1"}]
},
{ title:"First post", body:"first post user1", username:"user10", comments:[
  {username:"user1", body:"comment1 user1 post1"},
  {username:"user1", body:"comment2 user1 post1"}]
},
{ title:"First post", body:"first post user1", username:"user11", comments:[
  {username:"user1", body:"comment1 user1 post1"},
  {username:"user1", body:"comment2 user1 post1"}]
},
{ title:"First post", body:"first post user1", username:"user12", comments:[
  {username:"user1", body:"comment1 user1 post1"},
  {username:"user1", body:"comment2 user1 post1"}]
},
{ title:"First post", body:"first post user1", username:"user13", comments:[
  {username:"user1", body:"comment1 user1 post1"},
  {username:"user1", body:"comment2 user1 post1"}]
},
{ title:"First post", body:"first post user1", username:"user14", comments:[
  {username:"user1", body:"comment1 user1 post1"},
  {username:"user1", body:"comment2 user1 post1"}]
},
{ title:"First post", body:"first post user1", username:"user15", comments:[
  {username:"user1", body:"comment1 user1 post1"}]
},
])

```

2. Insertar al menos 10 nuevos usuarios:

```
db.users.insertMany([
{ username: "user1", email:"user1@gmail.com", age:25},
{ username: "user2", email:"user2@gmail.com", age:26},
{ username: "user3", email:"user3@gmail.com", age:27},
{ username: "user4", email:"user4@gmail.com", age:28},
{ username: "user5", email:"user5@gmail.com", age:29},
{ username: "user6", email:"user6@gmail.com", age:30},
{ username: "user7", email:"user7@gmail.com", age:31},
{ username: "user8", email:"user8@gmail.com", age:32},
{ username: "user9", email:"user9@gmail.com", age:33},
{ username: "user10", email:"user10@gmail.com", age:34},
])
```

## ACTUALIZAR DATOS

3. Actualiza todos los campos de una publi.

```
db.posts.updateMany({ title: ' Otro post15' }, { $set:{title: 'Es el nuevo 15', body: 'Mariposa', username: 'user4'}});
```

4. Cambia el body de una publi.

```
db.posts.updateOne({ title: ' Otro post14'}, { $set: { body:'Modificamos el body del post 14'}});
```

5. ACTUALIZAR COMENTARIOS. Cambia el body de un comentario.

```
db.posts.updateOne({ title: 'Otro post14'}, { $set: { body:'Modificamos el body del post 14'}});
```

6. ACTUALIZAR USERS. Actualiza todos campos de un usuario.

```
db.users.updateMany({ username: 'user9' }, { $set: { username: 'nuevo user9', email: 'user9bis@gmail.com', age: 42 } });

```

7. Cambia el mail de los usuarios

```
db.users.updateMany({username:'user5'},{ $set:{email:'user5bis@gmail.com'}):
```

```
db.users.updateMany({username:'user6'},{ $set:{email:'user6bis@gmail.com'}});
```

8. Aumenta en 5 la edad de un usuario.

```
db.users.update({username: 'user10'},{ $inc:{age:5}});
```

## OBTENER DATOS

9. Selecciona todas las publis.

```
db.posts.find()
```

10. ● Selecciona las publicaciones que coincidan con el username indicado.

```
db.posts.find({username:'user4'})
```

11. Seleccione todos los usuarios con una edad mayor a 20.

```
db.users.find({age:{$gte:20}})
```

12. Seleccione todos los usuarios con una edad inferior a 23.

```
db.users.find({age:{$lt:23}})
```

13. Seleccione todos los usuarios que tengan una edad entre 25 y 30 años.

```
db.users.find({$and:[{age:{$gt:25}}, {age:{$lt:30}}]})
```

14. Muestra los usuarios de edad menor a mayor y viceversa.

```
db.users.find().sort({age:1})

```

```
db.users.find().sort({age:-1})

```

15. Seleccione el número total de usuarios.

```
db.users.countDocuments();

```

16. Seleccione todas las publicaciones de la siguiente manera: Título de la publicación: "título de las publicaciones".

```
db.posts.find().forEach((post) => {
  print("Titulo de la publicación:" + post.title)
})

```

17. Selecciona sólo 2 ussuarios.

```
db.users.find().limit(2);
```

18. Busca por title 2 publicaciones.

```
db.posts.find({ $or:[{title: " Otro post14"},{title: "Es el nuevo 15"}]});

```

## BORRAR DATOS

19 Elimina a todos los usuarios con una edad mayor a 30

```
db.users.deleteMany({age;{$gt:30}})
```

## EXTRA

20. Seleccione el número total de publicaciones que tienen más de un comentario.

```
db.post.find( { comments: {$size: 2} } )
```

21. Seleccione la última publicación creada

```
db.posts.find().sort({_id:-1}).limit(1);
```

22. Selecciona 5 publicaciones y que sean las últimas creadas.

```
db.posts.find().sort({_id:-1}).limit(5);
```

23. Elimina todas las publicaciones que tengan más de un comentario.

```
db.posts.deleteMany({comments: {$size:2}});
```
