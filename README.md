# VexCode API
This is UAA Robotic's documentation of the VexCode API! It's a work in progress.

### Contributing
Currently, contribution is only open to UAA Robotics members. However, soon we 
will open this documentation up for other teams to contribute.
<br> <br>

**Setup.** 
To edit, install docsify-cli to preview the website pages locally using `npm i docsify-cli -g` (if you don't have npm, you can download it through [node.js](https://nodejs.org/en/download)). Once installed, clone the [github repo](https://github.com/UAA-Robo/VEX-API). Then in that directory run `docsify serve` to preview the site locally in your browser.
<br> <br>

**Formatting.**
To add classes or methods to this repo, please follow the cpp/template.md format.
* Please use **method and parameter** descriptions from the actual comments in the vexCode code (as viewed in VSCode with the VEX extension). Group methods by either `Setting`, `Action`, or `Sensing`, similar to [this outdated documentation](https://help.vexcodingstudio.com/index.html).

* Use **vex type descriptions** that are in the [VEXcode API](https://api.vexcode.cloud/v5/namespace/namespacevex). 

* Keep **examples** simple and make sure to test them. Each example should be a fully functioning block of code that can be run in main as is (that means include every variable declaration). Use comments if you add specific parameters. Don't use `using namespace vex` or `using namespace std`. Variables should be in snake case and should start with `my_` (ex/ `my_motor`) to help clarify the difference between our example variables and vex variables.

<br>
After you edit the md files, and push to the main branch, your changes will automatically be deployed to the documentation website.


### Documentation for the Documentation
> [Here](https://www.markdownguide.org/cheat-sheet/) is a markdown cheat sheet. <br>
> [Here](https://docsify.js.org/#/quickstart) is the docsify docs.
