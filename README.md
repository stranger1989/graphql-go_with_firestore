# Go GraphQL ToDo to Google Firestore

A simple GraphQL queries and mutations to Google Firestore.

Run the main file, it will spawn a GraphQL HTTP endpoint

```
go run main.go
```

Execute queries via shell.

```
// To get single ToDo item by ID
curl -g 'http://localhost:8080/graphql?query={todo(id:"xxxxxxxxx"){id,text,done}}'

// To create a ToDo item
curl -g 'http://localhost:8080/graphql?query=mutation+_{createTodo(text:"create todo"){id,text,done}}'

// To get a list of ToDo items
curl -g 'http://localhost:8080/graphql?query={todoList{id,text,done}}'

// To update a ToDo
curl -g 'http://localhost:8080/graphql?query=mutation+_{updateTodo(id:"xxxxxxxxx",text:"update todo",done:true){id,text,done}}'
```

## Web App

Access the web app at `http://localhost:8080/`. It is work in progress and currently is simply loading todos by using jQuery ajax call.

## Use Grapiql

You can use grapiql electron app, And create graphql query by GUI.

```
brew cask install graphiql
```

## Version Info

```
go 1.14
github.com/graphql-go/graphql v0.7.9
cloud.google.com/go/firestore v1.1.1
```