# Warp Dev Space

This is a top level example workspace for warp dev. Common build scripts and inforamtion is here.  This enviornmenet will pull in any additional repositories as needed.  

Each unique build enviroment for a major component will have a top level directory under which the relevant repositories will be placed. 

All tooling should be driven from simple makefiles.  Makefiles may invoke the common tooling for the language of choice.  Makefiles should be as simple as possible. Make use of scripts and tooling in this repository as necessary

## Directory Template structure

### Workspaces for applications and components
- wsgo -- workspace for primary Go applications and components

### scripts
- bscripts -- build time scripts used during development only
- dscripts -- scripts that get used in deployment environments

### tools
Custom applicatins used during development (note: deployment tools should be treated like any deployed applicaiton

# Documentation
There are developmer documentation and user documenation. In both cases projects should have procedures to generate documentation to target for a single top level HTTP server with browser viewable documentation and generated to be self hosted outside the development environment.  Where practical default to **Markdown** and any environment appropriate doc generator such as godoc, doxygen, javadoc, etc.
## Developer API docs
Generated via the appropriate document generator allowing for docs embedded in the source file 
- eg: godoc, doxygen, javadoc, etc

# LICENSE
Each directory will either have its own LICENSE or will adopt the LICENSE file of the directory above it. Individual files may have their own license embedded in the file thus the precedance for licesnes is:
- File --> directory --> parent-directory
by default the LICENSE will be Apache 2.0

