In the era of web development Node.js plays a major role in the industry there are a lot of frameworks that support Node.js but when it comes to Test Automation there are only a few tools that are available in the market majority of the Organisation use Selenium as there Tool for Automation as it is open source and supports the wide community but selenium too has many disadvantages like Handling Page loads, managing different waits also managing different drivers for different browsers. Here comes into the picture a new tool named “Testcafe”. Testcafe is a product of DevExpress which is built on top of Node.js to automate End to End web testing which overcomes all the major challenges faced using Selenium.

What is Testcafe?

Testcafe is a free and open-source Node.js tool to automate end to end scenarios.
It runs on Windows, macOS, and Linux.
Testcafe uses a proxy that performs URL rewriting and injects the testcript into the browser since these proxies manage all cookies/storage for the tests so we get a clean and isolated test environment.
 
Why use Testcafe?

Supports Multiple Browser for Parallel Execution.
One does not need to care about waiting for an element on the page to load.
Supports Page Object Model, Data-Driven, and BDD.
Compatible with Continuous Integration Systems like Jenkins, Teamcity, Travis, Github Actions, etc.
 
Setup:- As we know that Testcafe is built on top of Node.js so setup is too easy with just one npm command [npm install testcafe] and the world of Automation is all yours. The best part is that there is no requirement for installing web drivers and additional Libraries. Tescafe invokes the browser installed in the machine and runs the Tests.

Development Languages:-There is no doubt that Javascript is the most widely used as the language on the web which means using the same language for automation will give benefits too.
Testcafe Supports JavaScript as well as Typescript for writing Automation test cases.Testcafe automatically compiles Typescript before running the tests so that you do not need to compile the typescript code explicitly.

Browser Support:- Testcafe supports all the browsers like Chrome,FireFox,Internet Explorer and Safari. Moreover it supports Mobile Browsers as well, also the browser support is for both UI and Headless.

Installing Testcafe:-
Step1:-Create a new Project Folder{example: Testcafe Automation}

Screenshot_1

Step2:-Download VSCode on your machine and open it.
Step3:-Now on VSCode go to File option→ Open Folder→ Select the project folder you Created.
Step4:-Now Click on Terminal And Proceed with following steps to install via NPM.
Step5:-Install via NPM:

NPM must be installed on your environment first, to install the Cypress. NPM is the package manager for JavaScript and the world’s largest software registry.
Once NPM is installed please run the following command:
cd/your/project/path
npm install–save-dev testcafe

Writing First Test

Screenshot_1 (1)

Running the Test
On Package.JSON file under scripts tag add the following Command

Testcafe chrome test.js
0r we can also define the following inside the scripts tag of package.json file

“scripts”:{
“Test:chrome”: “tescafe chrome ./test/Basictest.js”
}
and execute the command

npm run Test:chrome
from the terminal to run the Basictest.js file.

We can see the following result after Running the above command above.

unnamed

Adding Screenshots to the Failing Tests
To attach screenshots to the failing we create testcaferc.json file to define the Screenshot path and screenshot path pattern.

Screenshot_3

Then on the scripts tag, we need to add one command

“scripts”:{
“Test:chrome”: “tescafe chrome ./test/Basictest.js -s takeOnFails=true
”
}
The output for the failing screenshot looks like this:

unnamed (1)

Support to headless mode:
Testcafe provides support to run the test cases in Headless mode too just need to add the following command in the scripts tag:

“scripts”:{
“Test:chrome”: “tescafe chrome ./test/Basictest.js -s takeOnFails=true
”,
“Test:chrome:headless”: “tescafe chrome:headless ./test/Basictest.js -s takeOnFails=true
”
}
Now run the following command using the terminal

npm run Test:chrome:headless
Support to the mobile browser:
Testcafe provides support to run the test cases in the Mobile browser too and we just need to add the following command in the scripts tag:

“scripts”:{
“Test:chrome:mobile”:
”testcafe chrome:emulation:device=iphoneX ./test/Basictest.js -s takeOnFails=true
”
}
Now run the following command using the terminal

npm run Test:chrome:mobile
Support to Cross Browser testing:
Testcafe provides support to run the test cases in multiple browsers with just one command we can simulate the process

“scripts”:{
“Test:multiplebrowser”:“tescafe chrome,firefox ./test/Basictest.js -s takeOnFails=true
”
}
Now run the following command using the terminal

npm run Test:multiplebrowser
