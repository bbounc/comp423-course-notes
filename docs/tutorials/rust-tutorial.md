# Setting up a dev container for <Insert: Go or Rust depending on which you are doing>

* Primary author: [Brian Bordeaux](https://github.com/bbounc)

# Rust Tutorial for COMP423

Welcome to the Rust tutorial! In this guide, you'll learn how to set up a Rust development environment using a Dev Container, create a simple "Hello COMP423" program, and run it.

---

## Prerequisites

Make sure to have the follwing:

- **Docker** installed and running on your machine.
- **Visual Studio Code (VSCode)** 
- Basic knowledge of Rust programming.
- A GitHub account.
- Install Dev containers extension in vs code 

---

## Step 1: Setting Up the Dev Container

We'll use a Dev Container to create a consistent development environment for our Rust project.

### 1.1 Create the `devcontainer.json` File

First we need to create a Git repository. In order to do this run:


**git init**

Now create a new github repo through the website

Then in the vs code terminal run 


**git remote add origin https://github.com/<your-username>/comp423-course-notes.git**

**git remote add origin https://github.com/<your-username>/comp423-course-notes.git**

Then create a .devcontainer folder and inside of that create a devcontainer.json file

Then inside of this file paste this:


**{
  "name": "COMP423 Course Notes",
  "image": "mcr.microsoft.com/devcontainers/rust:latest",
  "customizations": {
    "vscode": {
      "settings": {},
      "extensions": [
        "rust-lang.rust-analyzer"  // Official Rust analyzer extension
      ]
    }
  }
}**

-name: This is simply the name of the container your working in and helps you keep containers organized when you have m ultiple
-image: This tell you whats going into your docker container in this case it is everything we need in order to work with rust 
-custiomization/vscode/extensions: This block allows us to add the rust analyiser extension with helps with the general coding processes with things like error checking

## Step 2: Writing the Rust program

Now that we are setup lets make our rust project. First we need to make a new directory to store the project. This can be done by using 


**cargo new hello_comp423 --bin --vcs none**

hello_comp423 is the project name
--bin tell us this is a binary project
-vcs none tells cargo not to make a repo for you automatically

You should also use the command rustc --version to make sure you have a recent version of rust.

Now open the hello_comp423 directory then open the src directory, finally open the main.rs file and paste this in


**fn main() {
    println!("Hello COMP423");
}**

Now run cargo build in your terminal this will compile your project and make the exectuable target/debug directory

Finally to run the program you will do cargo run in the terminal where you should see the output Hello COMP423

The diffrence between cargo build and cargo run is that cargo build puts the files together in a way that your machine can actually execuate them while cargo run actually executes the files which causes the program to run

