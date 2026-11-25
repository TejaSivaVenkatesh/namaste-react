1. Package.json:
It is a configuration of our project.
It contains the packages that we are using in the project with the package versions
Even dependency list will be mentioned
Any simple project can be turned to an npm project by npm init
2 types of dependencies in package.json
Dev dependencies
It is generally required for development
Normal dependencies
These will be used in production and Dev.
Caret(^), tilde (~) used before version number.
With Caret(^) usage Parcel upgrades it to patch/minor versions - Recommended
With Tilde(~) usage Parcel upgrades it to major versions.
In a project how many package.json will be there?
So many. One is in the actual project but there will be one in each npm package.

2. Package-lock.json
It keeps track of the exact version of the dependency.


3. Difference between package.json Vs package-lock.json
There is a small difference between both of these.
Package.json works like a directory of packages that that needed for the project. When npm install is executed the npm looks into package.json and see the list of required packages and for exact versions it will look into package-lock.json.




4. Bundle (Webpack/parcel/ Vite):
Create react app uses webpack behind the scenes to build the project structure.
But here we are using parcel package
What do bundlers do?
They minify, bundle, chunking and clean the code which is code ready to be shipped.
Parcel does,
Dev build
Local server
HMR - Hot Module Replacement. How?
Parcel watches the file changes using the file watching algorithm - Written in C++
Consistent Hashing
Bundling
Caching
Code splitting
Minification
Differential bundling
Image optimization
Diagnostics
Error handling and display
Hosting capability on HTTS
Lazy dev builds
Tree shaking




5. Transitive dependencies Vs Direct dependencies
Ex: my project needs react package - direct dependency
In node_modules > react folder there will be package.json and listed down some dependencies of react folder. Those are called transitive dependencies

6. What all files we put in GitHub?
We don’t put any regeneratable files. Ex: node_modules as we can generate them easily if we have package.json and package-lock.json.
But package.json and lock.json can't be regenerated. So we put them on GitHub.



7. What does the npx do?
It downloads the respective package from the remote temporarily, execute it and remove it.

8. What is Parcel?



9. What are React and ReactDOM CDN Links?
React is a Core react package where it contains all the operations that we do.
React DOM is a package where we do all the DOM related operations. It is like a bridge between react & browser.
createRoot
CreatePortal
Render
findDOMNode
flushSync

10. React.createElement
It is a core thing of creating an element.
React.createElement(“h1”, {}, “This is a heading tag”)

11. Creating a root
React.createElement(“h1”, {id: “heading”, xyz: “abc”}, “This is a heading tag” )

Nested elements:
<div id=”parent”>
<div id=”parent”>
<h1>This is a heading</h1>
</div>
</div>
React.createElement(“div”, {id: “parent”}, 
React.createElement(“div”, {id: “child”}, 
React.createElement(“h1”, {id: “heading”}, “This is a heading” )))




12. Why are there 2 different repos in React like react, reactDOM?
React splits its code into two libraries because React builds the blueprint in memory, while ReactDOM connects that blueprint to a web browser.
1. Why are React and ReactDOM separate libraries?
React is designed to work on multiple platforms—not just web browsers. Separating the core engine from the platform renderer allows you to reuse the exact same React logic anywhere:
React (Core Library): Handles components, state, hooks, and creates lightweight JavaScript objects (the Virtual DOM) using React.createElement. It has zero knowledge of HTML, browsers, or mobile screens.
ReactDOM (Browser Renderer): Acts as the bridge between React and the browser's Document Object Model (DOM). Methods like ReactDOM.createRoot and root.render translate React's virtual objects into real HTML tags on a webpage.
Other Renderers: Because React is separate, mobile developers can swap out ReactDOM for React Native to render native iOS/Android views, or React Three Fiber to render 3D WebGL graphics—all using the exact same React core library.

React is a common repo for any type of architecture but for mobile apps, webGL etc,. It change



13. How to initialize the repo as a git repository?
Git init - Initializing the normal repo to git repo
Git branch -M main - Setting up the main as a main/primary branch


