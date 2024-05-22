# Cargo Package Manager Integration with Artifactory
A repo to demonstrate Rust's package manager, Cargo, and how it integrates with Artifactory.

# Project Goal
The two Rust projects in this folder will demonstrate the basics of integrating Rust's package manager, Cargo, with 
Jfrog's Artifactory.

# Project Structure
This repo will hold two projects: an ["Inner Source"](https://en.wikipedia.org/wiki/Inner_source) library, to be built and published with Artifactory's Cargo 
integration, and a "Production" application that will incorporate the library.

## Inner Source Library
A simple library that will return a randomly-selected quote from the late, great [Yogi Berra](https://en.wikipedia.org/wiki/Yogi_Berra)

## Production Application
A basic Rust application that will incorporate the Inner Source library.  

## Pre Reqs (Local Build)
1. Install Cargo
2. Configure Cargo
3. Setup `~/.cargo/credentials`
```toml
 [registries.artifactory]                                                  
 token = "Bearer <access token>"
                  
 [registry]         
 token = "<access token>"   
```
4. 
## Steps
1. Create the library
```bash
cargo new --lib jfrog_quotes
```
2. Create the app
```bash
cargo new jfrog_app
```
3. Build the Library
```bash
cargo build --release
```
5. Publish the Library
```bash
cargo publish --registry artifactory
```

