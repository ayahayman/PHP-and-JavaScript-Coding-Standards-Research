--------------------------------------------------------------------------------------------------------------

Introduction:

    Coding standards are a set of rules for writing code consistently. These guidelines decrease errors and enhance the readability and maintainability of code. With a focus on best practices, style guidelines, and standard conventions, this study discusses PHP and JavaScript coding standards.

--------------------------------------------------------------------------------------------------------------

PHP Coding Standards:

--------------------------------------------------------------------------------------------------------------

Best Practices:

    1- Use Strict Typing: Enable strict typing to avoid unexpected type conversions.

    PHP is a loosely typed language, also known as a dynamically typed language, where the variables are not
    restricted to a particular data type at compile-time. On the other hand, strictly typed language is a programming language in which variables have to be declared with a certain data type at compile-time.
    
    To enable Script Typing in PHP, place this declaration at the very beginning of your PHP file or code block.

        declare(strict_types=1);

    Strict typing aids in avoiding unforeseen type-related problems that may result in incorrect behaviour or runtime errors. It guarantees that you work with the expected data types at all times.

    ----------------------------------------------------------------------------------------------------------

    2- Follow PSR Standards: Adhere to PHP-FIG standards like PSR-1, PSR-2, and PSR-12 for coding style and PSR-4 for autoloading.

    The PHP Framework Interoperability Group (PHP-FIG) created the PHP Standards Recommendations (PSRs) as a set of principles to encourage uniformity and interoperability among PHP applications. These guidelines address a number of topics related to PHP development, such as interfaces, autoloading, and coding style.

    ----------------------------------------------------------------------------------------------------------

    3- Use Namespaces: Organize code using namespaces to avoid name collisions

    PHP Namespaces are a means of enclosing items so that name conflicts can be avoided when using the same names repeatedly.

    In many contexts, it is viewed as an abstract idea. It allows redeclaring the identical functions, classes, interfaces, and constant functions in a different namespace without resulting in a fatal error. A namespace is declared as the following example:

        namespace MyApp\Utilities;

    ----------------------------------------------------------------------------------------------------------

    4- Error Handling: Use exceptions for error handling instead of error codes.

    Exception handling is the process of altering the regular course of code execution in the event that an error or other exceptional condition arises.

    PHP looks for the corresponding "catch" block and stops executing the code after it when an exception is triggered. The following code shows an example of how exception handling is implemented in PHP:

        try {
            // Code
        }
        catch (Exception $e) {
            // Handle exception
        }

    A fatal error along with the message "Uncaught Exception" will be displayed if an exception is not caught.

--------------------------------------------------------------------------------------------------------------

Style Guides:

    1- PSR-12 Extended Coding Style: Expands on PSR-1 and PSR-2, addressing formatting of control structures, line length, and indentation.

    2- PEAR Coding Standards: This style guide is also extensively utilised, especially for codebases that are legacy.

--------------------------------------------------------------------------------------------------------------

Common Conventions:

    1- CamelCase for Variables and Functions: Use camelCase for naming variables and functions.

    The first word in camel case should be lowercased to begin with. The initial letter of each subsequent word is then capitalised. As a result, the second word and every word that comes after it begin with a capital letter. 

        $userName = "John";
        function getUserName() { /* ... */ }

    The variable called "userName" and the function "getUserName" have been written with the CamelCase convention.

    2- PascalCase for Classes: Use PascalCase for class names.

    Pascal and camel cases are quite similar. The initial letter of the first word in Pascal case must likewise be capitalised, which is the only distinction between the two. Hence, in contrast to camel case, where the first word is in lowercase, every word in pascal case begins with an uppercase letter. It is usually used for classes as shown in the following:

        class UserAccount { /* ... */ }

--------------------------------------------------------------------------------------------------------------

Good and Bad Coding Practice Examples:

    Good Practice:

        declare(strict_types=1);

        namespace MyApp\Utilities;

        class UserAccount {
            private $userName;

            public function __construct(string $userName) {
                $this->userName = $userName;
            }

            public function getUserName(): string {
                return $this->userName;
            }
        }

    ----------------------------------------------------------------------------------------------------------

    Bad Practice:

        <?php

        class useraccount {
            var $UserName;

            function UserAccount($UserName) {
                $this->UserName = $UserName;
            }

            function GetUserName() {
                return $this->UserName;
            }
        }

--------------------------------------------------------------------------------------------------------------

JavaScript Coding Standards:

--------------------------------------------------------------------------------------------------------------

Best Practices:

    1- Use "const" and "let": Avoid using "var" to declare variables.

    Var: 
        The var keyword allows you to declare variables that are either globally or functionally scoped; block-level scope is not supported. This implies that a variable defined inside an if statement or loop could be accessed from outside the block and unintentionally redefined, which could result in a malfunctioning programme. The var keyword should generally be avoided.

    Let:
        Because both the var and let keywords enable you change the value at a later time, they are similar to each other in many respects. The primary distinction between the two is that let operates within a block scope; while it is reassignable, it cannot be redeclared.

    Const:
        The const keyword is blocked scoped, just like the let keyword. Nevertheless, if a variable is declared with the const keyword, it cannot be reassigned or redeclared. As a result, at the moment of declaration, a value must be assigned to each const variable.

    Example:

        const name = "John";
        let age = 25;

    ----------------------------------------------------------------------------------------------------------

    2- Arrow Functions: Use arrow functions for anonymous functions.
    
    The JavaScript function writing process can be enhanced by using the arrow function syntax in the following ways:

        - You can write shorter functions with greater clarity.
        - The return statement for single-line functions may be implied.
        - The keyword 'this' is not restricted to any one function.

    This code shows how to use the arrow function for a simple mathematical addition function:

        const add = (a, b) => a + b;

    ----------------------------------------------------------------------------------------------------------

    3- Strict Equality: Use "===" and "!==" instead of "==" and "!=". 

    When evaluating if its two operands are equal, the strict equality (===) operator returns a Boolean value. Different operands of different kinds are always regarded as different by the strict equality operator, in contrast to the equality operator.

    In the following code, age must be an integer and of value = 25 in order for the condition to return true:

        if (age === 25) { /* ... */ }

    Another example that clarifies the difference:

        "hello" === "hello"; // true
        "hello" === "hola"; // false

        3 === 3; // true
        3 === 4; // false

        true === true; // true
        true === false; // false

        null === null; // true

--------------------------------------------------------------------------------------------------------------

Style Guides:

    1- Airbnb JavaScript Style Guide: One of the most popular and comprehensive style guides.As evidence of its usefulness and general acceptability, it has grown to become one of the most starred JavaScript style guidelines on GitHub since its release.

    2- Google JavaScript Style Guide: Another widely used style guide with a strong emphasis on consistency. It provides guidelines on code formatting, best practices, and conventions to help developers produce consistent and high-quality code.

--------------------------------------------------------------------------------------------------------------

Common Conventions: JavaScript's common conventions are very similar to PHP's

    1- CamelCase for Variables and Functions: Use camelCase for naming variables and functions.

        const userName = "John";
        function getUserName() { /* ... */ }

    2- PascalCase for Classes: Use PascalCase for class names.

        class UserAccount { /* ... */ }

--------------------------------------------------------------------------------------------------------------

Good and Bad Coding Practice Examples:

    Good Practice:

        class UserAccount {
            constructor(userName) {
                this.userName = userName;
            }

            getUserName() {
                return this.userName;
            }
        }

        const user = new UserAccount('John');
        console.log(user.getUserName());

    Bad Practice:

        function useraccount(userName) {
            this.UserName = userName;
        }

        useraccount.prototype.GetUserName = function() {
            return this.UserName;
        }

        var user = new useraccount('John');
        console.log(user.GetUserName());

--------------------------------------------------------------------------------------------------------------

Conclusion:

    Maintainability and code quality are improved when PHP and JavaScript coding standards are followed. Adhering to style guides, common rules, and best practices guarantees uniformity and comprehensibility among codebases.

--------------------------------------------------------------------------------------------------------------

References:

1-  "Why Use declare(strict_types=1) in PHP? Fast Tips" from Inspector.dev: [Link](https://inspector.dev/why-use-declarestrict_types1-in-php-fast-tips/)

2-  "Introduction to PHP Standard Recommendation (PSR)" from Specbee: [Link](https://www.specbee.com/blogs/introduction-php-standard-recommendation-psr)

3-  "PHP | Namespace" from GeeksforGeeks: [Link](https://www.geeksforgeeks.org/php-namespace/)

4-  "PHP Exception Handling" from W3Schools: [Link](https://www.w3schools.com/php/php_exception.asp)

5-  "Snake Case vs Camel Case vs Pascal Case vs Kebab Case – What's the Difference?" from freeCodeCamp: [Link](https://www.freecodecamp.org/news/snake-case-vs-camel-case-vs-pascal-case-vs-kebab-case-whats-the-difference/)

6-  "JavaScript – var, let, or const? Which one should you use?" from Codeburst: [Link](https://codeburst.io/javascript-var-let-or-const-which-one-should-you-use-2fd521b050fa)

7-  "Strict equality (===)" from MDN Web Docs: [Link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_equality)

--------------------------------------------------------------------------------------------------------------