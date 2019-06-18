# guideline

## purpose

produce quality code for better maintenance

## setup

### Chrome

install `Chrome` from `google.cn/chrome`

go to `crx4chrome.com` and download `Setupvpn`

go to `chrome://extensions/`, turn on the `developer mode`, drag the crx file into the frame, and finish the installation.

register an account for Setupvpn

### Node

go to `http://nodejs.org/` and download `LTS` version of node, and install.

### vscode

install `vscode` from `https://code.visualstudio.com`

go to vscode extension and install:

`Babel JavaScript`

`Import Cost`

`IntelliSense for CSS class names in HTML`

`JavaScript (ES6) code snippets`

`Material Icon theme`

`Node.js Modules Intellisense`

`npm Intellisense`

`One Monokai Theme`

`Path Intellisense`

`Prettier - Code formatter`

`Sass`

`SCSS IntelliSense`

`StandardJS - JavaScript Standard Style`

`Visual Studio IntelliCode`

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

### naming2

Hidden variable : use `_` at the beginning of the variable name:

Like `let _time, _atom, _loopHelper`

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

## Split

Frontend developer -> visit `frontend.md`

backend developer -> visit `backend.md`
