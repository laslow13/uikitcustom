# uikitcustom


Customize UIKit to create new themes
------------------------------------------------------------------------------------------------------------------------------

UIKit provides a way to customize its framework explained in their official docs. In this post we will try to extend the framework for custom theme development.

###Basic Setup
We will need [NodeJs](https://nodejs.org/en/) for using npm(Node Package Manager), [Bower](https://bower.io/) for web package management and [Gulp](http://gulpjs.com/) task runner. Details about them can be found in their respective websites.

Step1: Cloning of UIKit github code. If you have git installed in your system run ``` git clone https://github.com/uikit/uikit.git ``` or in case if you don't have git just download the zip folder.

Step2:  Run ``` npm install -g gulp ``` for global level gulp installation. Move inside the folder using command prompt or terminal. Run ``` npm install ``` , this will install/download all the dependencies of ```package.json``` file inside ```node_modules``` folder and ``` bower install ``` will install all the dependencies inside ```bower_components``` folder.

Step3: Check the folder structure ``` src``` folder will have all the source less files of UIKit, ```themes``` folder will have all the themes ``` default ```, ``` gradient``` etc. developed customizing ``` src ``` files. If you run ```gulp dist```  the ```dist``` folder will be created and this folder will have all the compiled css and minified css of the themes like ```default``` theme. ``` gulp sync ``` will run the application ```http://localhost:3000``` will open in the browser having livesync facility.

### Developing custom theme

Step1: Create a new folder ``` uikit/theme_hydrogen ```.

Step2: Create ``` uikit.less``` file, the main file to import other less files. Create ```customizer.less``` and ```customizer.json``` file use live customization of UIKit [Live Customization](http://localhost:3000/docs/customizer.html). For reference see ```themes/default``` folder ```customizer.less``` and ```customizer.json``` files.

Step3: For reference use ```themes/default/uikit.less``` and make changes in your own ```uikit.less``` file.

Step4: Say if we want to customize ```button.less``` , then we need to create that file inside our theme folder, make changes in variables like ```@button-height: 30px;``` , use hooks like ```.hook-button() { border-radius: 10px; }``` or use hook miscellaneous for creating extra class or element style.
```
.hook-panel-misc() {
  // new rule
    .uk-panel a { color: #f00; }
}
```
Step4: After making changes run ```gulp indexthemes``` and ```gulp dist -t theme_hydrogen```. You can see the compiled css and minified one inside ```dist``` folder.

Step5: Making style for your theme is the next step. Create ```custom/theme_hydrogen/styles/blue/style.less``` file and make changes to that file, like ```@button-background: blue``` and see the changes by running ```gulp sync```. Open ```localhost:3000/docs/customizer.html``` choose ```theme_hydrogen Blue ``` from the dropdown, see the changes and download the css file or minified css for use.

An working example link is given [Custom UIKit](https://github.com/asif633/uikitcustom).
  