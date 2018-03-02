# Simple Query
``` 
{
  user(id: "40") {
    id,
    firstName,
      age,
      company {
          id,
          name,
          description
        }
    }
 }
```

# Named Query with query fragment usage
```
query findCompany {
  apple: company(id: "1") {
    ...companyDetails
  }
  google: company(id: "2") {
    name,
    description,
    users {
      firstName
    }
  }
}
```

# Query fragments

```
fragment companyDetails on Company {
  id
  name
  description
}
```
# Mutations

## Add User
```
mutation {
  addUser (firstName: "Dude", age: 55) {
    id
    firstName
    age
  }
}
```
## Delete User
```
mutation {
  deleteUser (id: "ryUS79fpb") {
		id
  }
}
```
## Edit User
```
mutation {
  editUser (id: "23", companyId: "1") {
		id,
    firstName,
    age,
    company {
      id
    }
  }
}
```
