1. NPM is basically a catalog that points to where packages can be found (like on Github), particularly for projects built with Node.js, which is basically JavaScript that can work on the server-side because it can interact with the file system. It's become the primary package manager for both front-end and back-end Web development by its ease of use and its vast repository of packages that it links to.

2. It makes downloading and integrating libraries and frameworks into your projects much easier than doing it by hand. Doing it by hand meant having to find where to download the correct library or framework online, extracting the correct files and putting them in the right location in the project, and referencing to it in the code at the right time (dependencies had to be ordered correctly to avoid errors). NPM, on the other hand, makes the downloading, extraction, and placement of the files for the libary or framework automatic (only one command is neeeded to do so).

3. It's a command line tool, registry, and a Website. As a command line tool, it can be used without needing a GUI (graphical user interface), which requires less disk space and is navigated purely via the keyboard. As a registry, it acts as a database that lists where packages and their depencies are located. As a Website, it can be searched for packages and further info about those packages.

![A package page on the NPM Website](https://condescending-liskov-daaa2d.netlify.app/npm-page.png)

4. The package.json file is a list of metadata for a project, including the project title and description and what packages should be installed (and their minimum versions). It also allows the project creator to specify scripts to run upon entering certain commands like `start` or `run`. A related file is the package-lock.json file, which ensures that the exact versions of the packages are kept consistent. The package-lock.json file becomes highly important for teams, because if any team member had a different version of a package, the project might not work for them due to compatibility issues. Unless you're doing a project yourself, you should usually avoid deleting the package-lock.json file so everyone on your team can be on the same page with the correct package versions.

![A sample package.json file](https://condescending-liskov-daaa2d.netlify.app/packagejson.png)

5. The scripts section is where you declare build scripts, like `npm run dev`, as well as other scripts that you can run like test scripts. Running any of these scripts will start a command line process, which can include Unix binaries like `ls` (for listing items in a specific folder). Some script commands come built in like `start` and `test`. To run script commands that are not-built in, you need to use the syntax like `npm run myscript`. 

![An NPM build script being run in the command line](https://condescending-liskov-daaa2d.netlify.app/npm-run-script.png)

6. Dependencies are the packages that a project needs to run. Some are development dependencies, and others are production dependencies. The former includes build tools and anything else that is only needed when developing and testing. The latter includes any packages required for when the project is deployed for public use.

7. To install a specific dependency, all you need to do is enter `npm install <dependency_name>`. It will be installed, along with any of its own dependencies, in the node_modules folder. To uninstall a dependency, use `npm uninstall <dependency_name>`.

8. NPM will first look for script dependencies in the node_modules folder. If it can't find it in the node_modules folder, it will try and find it among globally installed packages (meaning packages that have been installed so they're available to any project on the system). It's best to avoid installing packages globally since most packages will only be needed by one or some of your Node projects.

![The output of the NPM outdated command, listing packages that are out of date for a project](https://condescending-liskov-daaa2d.netlify.app/npm-outdated.png)

9. 3 NPM commands include `init`, `outdated`, and `doctor`. The `init` command creates a package.json file for a project, by asking a few questions about the project, like the project name, version number, description, where to start script execution (also known as the entry point), the option to specify a testing command, git repository, keywords for locating the project, the author, and license. From there, one can start installing packages which will also be listed in package.json. The `outdated` command allows one to find out what dependencies have updates available that are not yet installed. This can be important if a package update includes security fixes, or adds a new feature that's needed for a project. The command also lists the location of outdated dependencies and states which packages depend on packages that have updates available. Finally, the `doctor` command is for auditing whether you can use NPM properly. According to `npm help doctor`, the requirements for NPM to function include:
    - NPM must be able to run Node and Git
    - The NPM registry, or another registry that uses the same API, is available to NPM
    - The user can create and modify the node_modules folder and its contents for each NPM project
    - NPM's cache is available and not corrupted

![The output of the NPM doctor command, which lists suggestions for making sure NPM is fully functional](https://condescending-liskov-daaa2d.netlify.app/npm-doctor.png)
