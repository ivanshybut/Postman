<<<<<<< HEAD
# Create method __get__, __post__, __put__, __delete__

## Base URL:  https://rahulshettyacademy.com 
## key =qaclick123
- 🔶POST:
1. ➡️ Resource: /maps/api/place/add/json
2. ➡️ Sample Body:


=======
# Script of method get, post, put, delete

## Base URL: https://rahulshettyacademy.com

- 🔶POST:
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
- 🔶GET:
  Статус код 200
   
```postman
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

```postman
pm.test("Verefication of status code", function () {
    if (pm.environment.get("placeID")) {
         pm.response.to.have.status(200);
         pm.test("Address is correct", function () {
            var jsonData = pm.response.json();
            pm.expect(jsonData.address).to.eql("29, side layout, cohen 09");
            });
    }else {
        pm.response.to.have.status(404);
        postman.setNextRequest(null);
    }
   
});
```
- 🔶PUT:
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

- 🔶DELETE:
  Статус код 200
   
```postman
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

```
postman.setNextRequest("Get Place");

```






  
>>>>>>> f43c62f65d7f773468d8ea7b24a0709238feda89
