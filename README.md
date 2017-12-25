# pspostmanfunda

create a variable, in postman, use
```
{{var}}
```

## 4. Testing Requests
### 3 Pre-built Tests
```
pm.test('200',function(){
    pm.response.to.have.status(2000);
})
```
```
pm.test('return 5', function(){
  const books = pm.response.json();
  pm.expect(books.length).to.eql(5);
})
```


```
const moment =require('moment');
const data = _.result(pm,'response.json')
pm.expect(moment(data.createAt).format("MM/DD/YYYY")).to.eql(moment().format('MM/DD/YYYY'))
```
## 5. Collections
### 9 Refactor: Loop Over Users
```
const users = data.users;
const user = _.sample(users);

pm.globals.set("email",user.email);
pm.globals.set("firstName",user.firstName);
pm.globals.set("lastName",user.lastName);
```

