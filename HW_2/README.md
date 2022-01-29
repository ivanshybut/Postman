# TESTS

## - 🔶Get:/first;


Статус код 200
  
```js
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
``` 
```js
pm.test("Body is correct", function () { 
    pm.response.to.have.body("This is the first responce from server!");
});
```
## - 🔶Post:/user_info_3;
Статус код 200
```js
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
Спарсить response body в json.
```js
var resp = pm.response.json();
```
Проверить, что name в ответе равно name s request (name вбить руками.)
```js
pm.test("The response name is equal to the request name", function() {
    pm.expect(resp.name).to.eql("Ivan");
});
```
Проверить, что age в ответе равно age s request (age вбить руками.)
```js
pm.test("The response age is equal to the request age", function(){
    pm.expect(resp.age).to.eql('29');
});
```
Проверить, что salary в ответе равно salary s request (salary вбить руками.)
```js
pm.test("The response salary is equal to the request salary",function(){
    pm.expect(resp.salary).to.eql(5500);
});
```
Спарсить request.
```js
var req = request.data;
```
Проверить, что name в ответе равно name s request (name забрать из request.)
```js
pm.test("The response name is equal to the request name", function() {
    pm.expect(resp.name).to.eql(req.name);
});
```
Проверить, что age в ответе равно age s request (age забрать из request.)
```js
pm.test("The response age is equal to the request age", function(){
    pm.expect(resp.age).to.eql(req.age);
});
```
Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```js
pm.test("The response salary is equal to the request salary",
    function(){
        pm.expect(resp.salary).to.eql(Number(req.salary));
});
```
Вывести в консоль параметр family из response.
```js
console.log(resp.family)
```
Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)
```js
pm.test("U_salary_1_5_year in the response is equal salary * 4 from the request", function(){
    pm.expect(resp.family.u_salary_1_5_year).to.eql(req.salary * 4)
});
```
## - 🔶Get:/object_info_3;

Статус код 200
```js
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
Спарсить response body в json.
```js
var resp = pm.response.json();
```
Спарсить request.
```js
var req = pm.request.url.query.toObject();
```
Проверить, что name в ответе равно name s request (name забрать из request.)
```js
pm.test("The response name is equal to the request name", function(){
    pm.expect(resp.name).to.eql(req.name);
});
```
Проверить, что age в ответе равно age s request (age забрать из request.)
```js
pm.test("The response age is equal to the request age", function(){
    pm.expect(resp.age).to.eql(req.age);
});
```
Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```js
pm.test("The response salary is equal to the request salary", function(){
    pm.expect(String(resp.salary)).to.eql(req.salary);
});
```
Вывести в консоль параметр family из response.
```js
console.log(resp.family);
```
Проверить, что у параметра dog есть параметры name.
```js
pm.test("The dog parameter has name",function(){
    pm.expect(resp.family.pets.dog).to.have.property('name');
});
```
- Проверить, что у параметра dog есть параметры age.
```js
pm.test("The dog parameter has age", function(){
    pm.expect(resp.family.pets.dog).to.have.property('age');
});
```
Проверить, что параметр name имеет значение Luky.
```js
pm.test("The name parameter is equal Luky", function(){
    pm.expect(resp.family.pets.dog.name).to.eql('Luky');
});
```
Проверить, что параметр age имеет значение 4.
```js
pm.test("The age parameter is equal 4", function(){
    pm.expect(resp.family.pets.dog.age).to.eql(4);
});
```

## - 🔶Get:/object_info_4;
Статус код 200
```js
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
Спарсить response body в json.
```js
var resp = pm.response.json();
```
Спарсить request.
```js
var req = pm.request.url.query.toObject();
```
Проверить, что name в ответе равно name s request (name забрать из request.)
```js
pm.test("The name parameter response is equal to the request name", function(){
    pm.expect(resp.name).to.eql("Ivan");
});
```
Проверить, что age в ответе равно age из request (age забрать из request.)
```js
pm.test("The age parameter response is equal to the request age", function(){
    pm.expect(resp.age).to.eql(29);
});
```
Вывести в консоль параметр salary из request.
```js
console.log(req.salary);
```
Вывести в консоль параметр salary из response.
```js
console.log(resp.salary);
```
Вывести в консоль 0-й элемент параметра salary из response.
```js
console.log(resp.salary[0]);
```
Вывести в консоль 1-й элемент параметра salary параметр salary из response.
```js
console.log(resp.salary[1]);
```
Вывести в консоль 2-й элемент параметра salary параметр salary из response.
```js
console.log(resp.salary[2]);
```
Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
```js
pm.test("The salary[0] parameter is equal the salary from the request", function(){
    pm.expect(resp.salary[0]).to.eql(Number(req.salary));
});
```
Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)
```js
pm.test("The salary[1] = (salary from the request) * 2", function(){
    pm.expect(Number(resp.salary[1])).to.eql(req.salary * 2);
});
```
Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
```js
pm.test("The salary[2] = (salary from the request) * 3", function(){
    pm.expect(Number(resp.salary[2])).to.eql(req.salary * 3);
});
```

- Создать в окружении переменную name

- Создать в окружении переменную age

- Создать в окружении переменную salary

- Передать в окружение переменную name
```js
pm.environment.set("name", "Ivan");
```
Передать в окружение переменную age
```js
pm.environment.set("age", "29");
```
Передать в окружение переменную salary
```js
pm.environment.set("salary", "5500");
```
Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.
```js
for(let i = 0; i < resp.length; i++){
    console.log(resp.salary[i]);
}
```
## - 🔶Post:/user_info_2;
- Вставить параметр salary из окружения в request
- Вставить параметр age из окружения в age
- Вставить параметр name из окружения в name
- Отправить запрос.

Статус код 200
```js
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
Спарсить response body в json.
```js
var resp = pm.response.json();
```
Спарсить request.
```js
var req = request.data;
```
Проверить, что json response имеет параметр start_qa_salary
```js
pm.test("The json parameter has the start_qa_salary", function(){
    pm.expect(resp).to.have.property("start_qa_salary");
});
```
Проверить, что json response имеет параметр qa_salary_after_6_months
```js
pm.test("The json response from the response has the qa_salary_after_6_months", function(){
    pm.expect(resp).to.have.property("qa_salary_after_6_months");
});
```
Проверить, что json response имеет параметр qa_salary_after_12_months
```js
pm.test("The json parameter from the response has the qa_salary_after_12_months", function(){
    pm.expect(resp).to.have.property("qa_salary_after_12_months");
});
```
Проверить, что json response имеет параметр qa_salary_after_1.5_year
```js
pm.test("The json parameter from the response has the qa_salary_after_1.5_year", function(){
    pm.expect(resp).to.have.property("qa_salary_after_1.5_year");
});
```
Проверить, что json response имеет параметр qa_salary_after_3.5_years
```js
pm.test("The json parameter from the response has the qa_salary_after_3.5_years", function(){
    pm.expect(resp).to.have.property("qa_salary_after_3.5_years");
});

```
Проверить, что json response имеет параметр person
```js
pm.test("The json parameter from the response has the person parameter", function(){
    pm.expect(resp).to.have.property("person");
});
```
Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)
```js
pm.test("The start_qa_salary is equal the salary from the request", function(){
    pm.expect(resp.start_qa_salary).to.eql(Number(req.salary));
});
```
Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)
```js
pm.test("The qa_salary_after_6_months is equal (the salary from request) * 2", function(){
    pm.expect(resp.qa_salary_after_6_months).to.eql(Number(req.salary) * 2)
});
```
Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)
```js
pm.test("qa_salary_after_12_months is equal salary * 2.7 from request", function(){
    pm.expect(resp.qa_salary_after_12_months).to.eql(req.salary * 2.7);
});
```
Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)
```js
pm.test("qa_salary_after_1.5_year is equal salary * 3.3 from request", function(){
    pm.expect(resp['qa_salary_after_1.5_year']).to.eql((req.salary) * 3.3);
});
```
Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)
```js
pm.test("The qa_salary_after_3.5_years =  salary * 8 from the request", function(){
    pm.expect(resp['qa_salary_after_3.5_years']).to.eql(Number(req.salary) * 3.8)
});
```
Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)
```js
pm.test("In the person u_name[1] is equal salary from the request", function(){
    pm.expect(resp.person.u_name[1]).to.eql(Number(req.salary));
});
```
Проверить, что что параметр u_age равен age из request (age забрать из request.)
```js
pm.test("The u_age parameter is equal age from the request", function(){
    pm.expect(resp.person.u_age).to.eql(Number(req.age));
});
```
Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)
```js
pm.test("The u_salary_5_years parameter is equal salary * 4.2 from the request", function(){
    pm.expect(resp.person.u_salary_5_years).to.eql(Number(req.salary) * 4.2);
});
```
- Написать цикл который выведет в консоль по порядку элементы списка из параметра person.
```js
for(var key in resp.person) {
   if(typeof(resp.person[key]) == 'object'){
       for(let i = 0; i < Object.keys(resp.person[key]).length; i++){
           console.log(resp.person[key][i]);
       }
   }
   else if(typeof(resp.person[key]) != 'object') {
        console.log(resp.person[key]);
   }
}
```