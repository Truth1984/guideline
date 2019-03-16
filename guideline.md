# guideline

## purpose

produce quality code for better maintenance

## setup

### vscode

install `vscode`
go to vscode extension and install:

`Babel JavaScript`

`Import Cost`

`IntelliSense for CSS class names in HTML`

`JavaScript (ES6) code snippets`

`Mobx/Rematch React Snippets`

`Node.js Modules Intellisense`

`npm Intellisense`

`One Monokai Theme`

`Path Intellisense`

`Prettier - Code formatter`

`Sass`

`SCSS IntelliSense`

`StandardJS - JavaScript Standard Style`

`Visual Studio IntelliCode - Preview`

go to file -> preference -> settings
search for `FORMAT ON SAVE` and select this option

### github

register an account on `github.com`
download git from `https://git-scm.com/`

## Format

### const, var, let

`const` for constant variable:
`const fs = require("fs");`

`let` for temporary variable, you should ALWAYS use it within a Function:
`for (let i = 0; i < 10; i ++)`

`var` for variable that will exist for long term & OUTSIDE the function:
`var config = {}`

### naming

`--- a name for variable should at least describe the functionality of this varible ---`

temporary variable (CANNOT EXIST PASSED 15 LINES OF CODE) : `let temp, _temp, temporary, tempCounter, tempInt, tempFloat;`

`Object` : `let obj, object, aSet, pair;`

`Boolean` : `let status, condition;`

`Array` : `let array, arr, aList;`

`Integer` : `let num, number, counter, length, aNum, aFloat;`

`String` : `let line, string, words, str;`

`Function` : `var functionDescription = () => {}`

### Function, If, Backtick, Return

#### Funciton

    // very bad
    var getArray = function (size) {
        return new Array(size);
    }

#### =>

    // get array version 1
    var getArray = () => {
       return new Array();
    }

    // get array v2
    var getArray = (size) => {
        return new Array(size);
    }

    // get array v3
    var getArray = (size = 0) => {
        return new Array(size);
    }

    // get array v4
    var getArray = (...sizes) => {
        let result = 0;
        for (let i of sizes){
            result += i;
        }
        return new Array(result);
    }
    
    // order array     
    var = orderWords = (ori_array)=>{
        // var ele = document.getElementById("words");
        // var ori_str = ele.textContent;
        // var ori_array = ori_str.split(" ");
        var words_array = [];
        for (i = 0; i < ori_array.length; i++) {
          if (ori_array[i].length > 2) {
            if (words_array.indexOf(ori_array[i].toLowerCase()) == -1) {
              words_array.push(ori_array[i].toLowerCase());
            } else {
              delete ori_array[i];
              console.log(i);
            }
          } else {
            delete ori_array[i];
          }
        }
        words_array.sort();
        ori_array.sort();
        for (i = 0; i < ori_array.length; i++) {
          if (words_array.indexOf(ori_array[i]) == -1 && ori_array[i]) {
            indextemp = words_array.indexOf(ori_array[i].toLowerCase());
            words_array[indextemp] = ori_array[i];
          }
        }
        console.log(ori_array.sort());
      }

#### If1

    // very bad
    if( 1+1 > 2){
        console.log("wrong")
    }else{
        console.log("corrent");
    }

    // OK for multi-line
    if(1+1>2){
        let line = "multi-line action";
        line += "action2";
        console.log(line);
    }else{
        console.log("other options");
    }

#### =>

    // v1
    1+1 > 2 ? console.log("wrong") : console.log("correct");

    //v2
    console.log( 1+1>2 ? "wrong" : "correct" );

#### If2

    // very bad
    if( 1+1 === 2 ){
        console.log("correct");
    }

#### =>

    if( 1+1 === 2 ) console.log("correct");

#### Backtick

    let a = "a", b = "b", c = "c";

    //very bad
    console.log(a+"\t"+b+c);

#### =>

    //v1
    console.log(a,"\t",b,c);

    //v2
    console.log(`${a} \t ${b} \${c}`);

#### Return

    let a = 50;

    //very bad
    if(a < 50){
        a = a + 1;
        return a;
    }else{
        return a-50;
    }

#### =>

    if (a < 50) {
        a = a + 1;
        return a;
    }
    return a - 50;
