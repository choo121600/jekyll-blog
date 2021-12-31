---
layout: post
type: tech
date: 2021-12-15 14:13
category: JavaScript
title: JavaScript ES6
tech-header: true
hash-tag: [JavaScript, WEB]
---

기존의 var는 변수 선언 방식에 있어서 큰 단점이 존재했다.
let은 블록범위의 변수를 선언한다.

<pre>
    <code id="sourcecode" class="javascript">
        var x = 10;
        // Here x is 10
        {
        let x = 2;
        // Here x is 2
        }
        // Here x is 10
    </code>
</pre>

var는 변수를 한 번 더 선언했음에도 에러가 나오지 않고 각기 다른 값이 출력되었다.

이는 변수가 어떻게 사용될지 파악이 힘들고 값이 바뀔 우려가 있다.

그래서 ES6부터는 변수 선언 방식을 용도에 따라 let과 const로 나누었다.

<pre>
    <code id="sourcecode" class="javascript">
        let city = "Seoul";
        console.log(city);
        // Seoul
        let city = "Busan";
        console.log(city);
        // SyntaxError
        city = "Busan";
        console.log(city);
        // Busan

        const country = "Korea";
        console.log(country);
        // Korea
        const country = "US";
        console.log(country);
        // SyntaxError
        country = "US";
        console.log(country);
        // TypeError
    </code>
</pre>

위의 예시를 보면 let는 변수 재할당이 가능하다.하지만 const는 변수 재할당이 불가능하다.

따라서 변수 재할당이 필요한 경우에 let을 사용하고 그렇지 않다면 const를 사용한다.


Arrow Functions

Example
<pre>
    <code id="sourcecode" class="javascript">
        //ES5
        var x = function(x, y) {
            return x * y;
        }

        //ES6
        const x = (x, y) => {
            return x * y
        };
    </code>
</pre>

for/ of Loop

<pre>
    <code id="sourcecode" class="javascript">
        const cars = ["bmw", "volvo". "Mini"];

        let text ="";

        for (let x of cars) {
            text += x + " "
        }
    </code>
</pre>

JavaScript set objects

<pre>
    <code id="sourcecode" class="javascript">
        // Create a Set
        const letters = new Set()
        // Add some values to the set
        letters.add("a")
        letters.add("b")
        letters.add("c")
    </code>
</pre>


JavaScript Classes

<pre>
    <code id="sourcecode" class="javascript">
        class ClassName {
            constructor(name, year){
                this.name = name;
                this.year = year;
            }
        }
    </code>
</pre>


Using Class

<pre>
    <code id="sourcecode" class="javascript">
        const myCar1 = new Car("Ford", 2014);
        const myCar2 = new Car("Audi", 2016);
    </code>
</pre>
