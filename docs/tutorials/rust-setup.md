# Setting up a dev container for Rust:

* Primary author: [Jack Coury](https://github.com/jcoury89)

* Reviewer: [Taylor Morris](https://github.com/Taylor1515)

* Site adapted from [Comp 423 MKdocs Tutorial](https://comp423-25s.github.io/resources/MkDocs/tutorial/#step-2-create-a-remote-repository-on-github)



## Phase 0: Local Software Setup (what you need on your computer and on the web)

1. **A GitHub account:**  
   If you don’t have one yet, [sign up at GitHub](https://github.com).

2. **Git installed:**  
   Install Git if you don’t already have it. [Download Git here](https://git-scm.com).

3. **Visual Studio Code (VS Code):**  
   Download and install it from [Visual Studio Code's website](https://code.visualstudio.com).

4. **Docker installed:**  
   Required to run the dev container. [Get Docker here](https://www.docker.com).

---

# Phase 1: Setup Repo and Dev Container

## Step 1: Create a Local Directory and Initialize Git

1. Open VS Code and type `Ctrl + Shift + \`` to open a new terminal.   
2. Create a new directory:  
   ```mkdir rust-project```
3.	Change into that directory (folder) with the command ```cd rust-project```  
4.	Initialize your Git repo with the command ```git init```  
5.	Create a README file by typing:  
    a.	```echo “#Rust Project” > README.md```   
    b.	```git add README.md ```  
    c.	```git commit -m “Initial commit with README”```    
6.	Create a Remote Repository on GitHub  
    &nbsp;&nbsp;&nbsp;&nbsp;a.	 Log in to your GitHub account and navigate to the Create a New Repository page and fill in the details as follows:  
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Repository Name: rust-project  
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Description: "Rust project jcoury ex00"  
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Visibility: Public  
7.	Click Create Repository
8.	Link your Local Repository to Github  
    a.	Add the GitHub repository as a remote with the command ```“git remote add origin https://github.com/<your-username>/rust-project.git”```, replacing <your-username> with your GitHub username  
    b.	Check your default branch name with the subcommand ```git branch```. If it's not main, rename it to main with the following command: ```git branch -M main```.   
    c.	Push your local commits to the GitHub repository with the following command ```git push –set-upstream origin main```.  
## Step 2:	Add Development Container Configuration    

1.	Open up the rust-project directory via: File>Open Folder  
2.	Install the Dev Containers extension for VS Code via the View tab.  
3.	Create a .devcontainer directory in the root of your project with the following file inside of this "hidden" configuration directory:  
        &nbsp;&nbsp;&nbsp;&nbsp;i.	.devcontainer/devcontainer.json  
        &nbsp;&nbsp;&nbsp;&nbsp;ii.	Copy the following code into your .json file  

```json
{
  "name": "Rust Development Environment",
  "image": "mcr.microsoft.com/devcontainers/rust:latest",
  "customizations": {
    "vscode": {
      "extensions": ["rust-lang.rust-analyzer"]
    }
  },
  "postCreateCommand": "rustc --version"
}
```
10. Great! Almost Done! Now just press ```Ctrl Shift P``` and type in ```Dev Containers: Reopen in Container```  
11. Once it has fully opened open up another terminal and type ```rustc --version```


# Phase 3: Write Your First Program!

1. Open up a new terminal and type ```cargo new hello --vcs none```  
    a. This creates a new folder with a file called main.rs inside it  
    b. Open up that file in your vs code file explorer and replace 'hello' with 'Hello COMP423', and save.   
2. Go to your project directory by typing into the terminal ```cd hello```   
3. Type ```cargo build``` into the terminal and then hit enter.   
    a. Cargo build compiles your program and creates an executable which it stores in another folder called 'target/debug' in your working directory.   
4. Run that executable in your terminal by typing ```cargo run``` or ```cargo run ./target/debug/hello```   
5. And Voila! you have written your first program in Rust!   
6. Dont forget to run through the git subcommands to push everything you created into your repo!   
    ```git add .```   
    ```git commit -m "my first rust program"```   
    ```git push -u origin main```


   