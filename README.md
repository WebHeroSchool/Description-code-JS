# 10 Правил написания кода на JavaScript
1.  **Горизонтальное выравнивание не поощряется (но не запрещается).**  
Эта практика допускается, но в целом не поощряется руководством по стилю от Google. Также не требуется поддерживать горизонтальное выравнивание в тех местах, где оно уже использовалось.  
Горизонтальное выравнивание это метод добавления различного числа дополнительных пробелов в вашем коде для того чтобы определенные токены появлялись строго под другими токенами на предыдущих строках.

* Плохой вариант:  
{  
  tiny:.... 42,    
  longer: 435,  
};

* Хороший вариант:  
{  
  tiny: 42,  
  longer: 435,  
};

2. **Больше не используйте var.**  
Объявляйте все переменные с помощью const или let. По умолчанию используется const, за исключением случаев, когда нужно переназначить переменную. Ключевое слово var не должно использоваться.

* Плохой вариант:  
var example = 42;

* Хороший вариант:  
let example = 42;

3. **Объявляйте переменные по одной.**

* Плохой вариант:
let a = 1, b = 2, c = 3;

* Хороший вариант:  
let a = 1;  
let b = 2;  
let c = 3;

4. **Используйте одинарные, а не двойные кавычки.**  
Всегда в коде скрипта используйте одинарные кавычки, если не требуется иного.
Двойные кавычки допустимы, если в этой же строке необходимо использовать апостроф (') или одинарные кавычки для других целей.

* Плохой вариант:  
let directive = "No identification of self or mission."

* Хороший вариант:  
let directive = 'No identification of self or mission.';

5. **Для создания объекта используйте фигурные скобки. Не создавайте объекты через конструктор new Object.**

* Плохой вариант:  
let item = new Object();

* Хороший вариант:  
let item = {};

6. **Создание обьекта на 3 и более элементов.**  
При создании обьектов, равно как и массивов, содержащих большое количество свойств(элементов), и тем самым образующих строки, длиной более 20 символов, необходимо выполнять ряд условий:  
-Открывающая скобка располагается на той же строке;
-Каждое свойство оформляется на новой строке;
-Пробел после двоеточия;
-Закрывающая скобка располагается на новой строке.

* Плохой вариант:  
let superman = {defaults: { clark: 'kent' }, type: 'alien', hidden: true};

* Хороший вариант:  
let superman = {  
    defaults: { clark: 'kent' },  
    type: 'alien',  
    hidden: true  
  };

7. **Не используйте символов продолжения строки для длинных строк.**  
Не используйте символы продолжения строки (т. е., обратный слэш для окончания строки внутри строкового литерала) как в обычных,так и в шаблонных строковых литералах. Несмотря на то что ES5 это допускает, это может привести к замысловатым ошибкам, если после слэша последует пробел. Кроме того, это менее понятно для читателя.

* Плохой вариант:  
  const longString = 'This is a very long string that /
      far exceeds the 80 column limit. It unfortunately /
      contains long stretches of spaces due to how the /
      continued lines are indented.';

* Хороший вариант:  
  const longString = 'This is a very long string that ' +  
      'far exceeds the 80 column limit. It does not contain ' +  
      'long stretches of spaces since the concatenated ' +  
      'strings are cleaner.';

8. **Используйте программную табуляцию (ее поддерживают все современные редакторы кода и IDE) из двух пробелов.**

* Плохой вариант:  
function() {  
∙∙∙∙let name;  
}

* Плохой вариант:  
function() {  
∙let name;  
}

* Хороший вариант:
function() {  
∙∙let name;  
}

9. **Избегайте однобуквенных имен функций.**  
Имена должны давать представление о том, что делает эта функция.

* Плохой вариант:  
function q() {  
  // ...код...  
}

* Хороший вариант:  
function query() {  
  // ...код...  
}

10. **Присваивайте метод прототипу вместо замены прототипа на другой объект.**  
Замена прототипа на другой объект делает наследование невозможным.

function Jedi() {  
  console.log('new jedi');  
}

* Плохой вариант:  
Jedi.prototype = {  
  fight: function fight() {  
    console.log('fighting');  
  },  
  block: function block() {  
    console.log('blocking');  
  }  
};

* Хороший вариант:  
Jedi.prototype.fight = function fight() {  
  console.log('fighting');  
};  
Jedi.prototype.block = function block() {  
  console.log('blocking');  
};
