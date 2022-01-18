# Script of method get, post, put, delete

## Base URL: https://rahulshettyacademy.com

- 🔶POST: (Add Place);

Статус код 200
  
```postman
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
``` 

Устанавливаем переменную в enviroment(переменная с каждым отправлнием запроса меняется).

```
pm.test("Set variabe", function () {
    var jsonData = pm.response.json(); 
    console.log('This is out jsonData', jsonData.place_id)
    pm.environment.set("placeID", jsonData.place_id);
});
```
- 🔶GET: (Get Place);
 
Статус код 200
   
```postman
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
Проверяем "address" с ответа в json
```
pm.test("Test address", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.address).to.eql("29, side layout, cohen 09");
});
```

Проверяем "name" с ответа в json

```  
pm.test("Test name", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.name).to.eql("Frontline house");
});
```
  Проверяем "website" с ответа в json
```
pm.test("Test website", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.website).to.eql("http://google.com");
});
```
  Проверяем "language" с ответа в json
```
pm.test("Test language", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.language).to.eql("French-IN");
});
```
- 🔶PUT: (Update Place);
  
Статус код 200
   
```postman
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
```postman
pm.test("Address successfully updated", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.msg).to.eql("Address successfully updated");
});
```

- 🔶DELETE: (Delete Place)

Статус код 200
   
```postman
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
- 🔶GET: (Get Place After Removing)

Статус код 404
  
```
pm.test("Status code is 404", function () {
    pm.response.to.have.status(404);
});

```


