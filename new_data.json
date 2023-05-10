// 1) Статус код 200
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

// 2) Проверка структуры json в ответе.

var schema = {  
  "type": "object",
  "properties": {
    "age": {
      "type": "integer"
    },
    "name": {
      "type": "string"
    },
    "salary": {
      "type": "array",
      "items": [
        {
          "type": "integer"
        },
        {
          "type": "string"
        },
        {
          "type": "string"
        }
      ]
    }
  },
  "required": [
    "age",
    "name",
    "salary"
  ]
}

pm.test("Validation_JSON_DATA", function () {
   pm.response.to.have.jsonSchema(schema);
});

// 3) В ответе указаны коэффициенты умножения salary, напишите тесты по проверке правильности результата перемножения на коэффициент.
var respData = pm.response.json();
var reqSalary = +request.data.salary;

var respSalary = respData.salary[0];
var respSalary_1 = +respData.salary[1];
var respSalary_2 = +respData.salary[2];

console.log(respData.salary)

pm.test("Salary eql reqSalary", function () {
    pm.expect(respSalary).to.eql(reqSalary);
});

pm.test("Salary[1] eql reqSalary*2", function () {
    pm.expect(respSalary_1).to.eql(reqSalary*2);
});

pm.test("Salary[2] eql reqSalary*3", function () {
    pm.expect(respSalary_2).to.eql(reqSalary*3);
});

// 4) проверить, что 2-й элемент массива salary больше 1-го и 0-го
if (respSalary_2 > respSalary_1){
    console.log("result=true")
}

if (respSalary_2 > respSalary){
    console.log("result=true")
}


