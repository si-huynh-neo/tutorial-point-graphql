## First example

```json
{
   students{
      id
      firstName
      lastName
      college{
         name
         location
      }
   }
}
```

## Basic greeting

- Basic

```json
{
  greeting
}
```

### A GraphQL schema

```json
{
   greeting
   students {
      id
      firstName
      lastName
   }
}
```

### Resolver

```json
{
   greeting
   students {
      id
      firstName
      lastName
   }
}
```

## Query

### Simple Query

```json

{
   students{
      id
      fullName
   }
}
```

### Nest query

```json
{
   students{
      id
      firstName
      college {
         id
         name
         location
         rating
      }
   }
}
```

### Variable query

```json
-- query
query Query($myname_Variable:String!) {
  sayHello(name:$myname_Variable)
}

-- param
{
   "myname_Variable": "Mohtashim"
}

```

### Enum variable query

```json
query query_to_setColor($color_variable:ColorType) {
   setFavouriteColor(color:$color_variable)
}

-- param
{
   "color_variable":"RED"
}
```

## Mutation

### Mutation

```json
mutation {
   createStudent(collegeId:"col-2",firstName:"Tim",lastName:"George")
}
```

### Retrieve 

```json
{
    studentById(id:"SyPZEyet_") {
    id
    firstName
    lastName
  }
}
```

### Mutataion and retrieve

```json

mutation {
   addStudent_returns_object(collegeId:"col-101",firstName:"Susan",lastName:"George") {
      id
      firstName
      college{
         id
         name
      }
   }
}
```

## Validation
### Validation fail

```json
--  mutation/query
mutation doSignUp($input:SignUpInput) {
   signUp(input:$input)
}

-- param
{
   "input":{
      "email": "abc@abc",
      "firstName": "kannan",
      "password": "pass@1234"
   }
}
```

### Pass validation

```json
--  mutation/query
mutation doSignUp($input:SignUpInput) {
   signUp(input:$input)
}

-- param
{
   "input":{
      "email": "abc@abc.com",
      "firstName": "kannan",
      "password": "pass@1234"
   }
}
```

