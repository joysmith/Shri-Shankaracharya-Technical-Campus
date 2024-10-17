<img src="assets/images/07/1.png" width="700">

<img src="assets/images/07/2.png" width="700">

<img src="assets/images/07/3.png" width="700">

<img src="assets/images/07/4.png" width="700">

<img src="assets/images/07/5.png" width="700">

```js
pragma solidity ^0.4.18;
```

<br>

<img src="assets/images/07/6.png" width="700">

<img src="assets/images/07/7.png" width="700">

<img src="assets/images/07/8.png" width="700">

```js
pragma solidity ^0.4.18;

contract JoyContract {

}
```

<br>

<img src="assets/images/07/9.png" width="700">

<img src="assets/images/07/10.png" width="700">

<img src="assets/images/07/11.png" width="700">

<img src="assets/images/07/12.png" width="700">

<img src="assets/images/07/13.png" width="700">

```js
pragma solidity ^0.4.18;

contract JoyContract {
    string name = "joy peter";
    uint age = 70;
}
```

<br>

<img src="assets/images/07/14.png" width="700">

<img src="assets/images/07/15.png" width="700">

<img src="assets/images/07/16.png" width="700">

<img src="assets/images/07/17.png" width="700">

```js
pragma solidity ^0.4.18;

contract JoyContract {
    string public name = "joy peter";
    uint public age = 70;

}
```

<br>

<img src="assets/images/07/18.png" width="700">

<img src="assets/images/07/19.png" width="700">

```js
pragma solidity ^0.4.18;

contract JoyContract {
    string name;
    uint age;

    // constructor function
     function JoyContract () public {
        name = "joy peter";
        age = 70;
    }

}
```

<br>

<img src="assets/images/07/20.png" width="700">

<img src="assets/images/07/21.png" width="700">

```js
pragma solidity ^0.4.18;

contract JoyContract {
    string name;
    uint age;

    // constructor function
     function JoyContract () public {
        name = "joy peter";
        age = 70;
    }

    // setter
    function setMessage(string _name, uint _age) public {
        name = _name;
        age = _age;
    }

    // getter
    function getMessage() public view returns (string, uint) {
        return (name,age);
    }

}
```

<br>

<img src="assets/images/07/22.png" width="700">
