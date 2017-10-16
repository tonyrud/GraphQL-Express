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

# Named Query
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