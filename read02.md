# Git tutorial
## version control system
*Version Control is a system that allows you to revisit various versions of a file or set of files by recording changes.*
 ### Types of version control
 1. Local Version Control: many years ago, programmers created Local Version Control systems. A Local VCS entails one database on your hard disk that stores changes to files.
 2. Centralized version control: this system entails a single server storing all changes and file versions, which can be accessed by various clients.
 3. Distributed Version Control: this type addresses the major vulnerability of the CVS: the server as a single point of failure.

 **Getting started with git**
 
 *here is a table that shows git download links for each operating system:

 |OS      | Download link |
| ----------- | ----------- |
| Windows     | [Download](http://git-scm.com/download/win)       |
| Linux  | [Download](http://git-scm.com/download/linux)       |
|Mac   | [Download](http://git-scm.com/download/mac)     |

#### setting up a Git repository
- Importing: you can import using command line or terminal by:
1. Switch to the target project’s directory, ex:

`$ cd test (cd = change directory)`
2.Use the git init command:

`$ git init`
 3. To start tracking these repository files, perform an initial commit by typing the following:

`$ git add *.c`

`$ git add LICENSE`

`$ git commit -m “any message here”`

- Cloning: You can also create a copy of an existing Git repository from a particular server by using the clone command with a repository’s URL:

`$ git clone https://github.com/test`

##### Work flow
**Local Repository Structure**

The local Git repository has three components:

1. Working Directory: The actual files reside here.
2. Index: The area used for staging
3. Head: Points to the most recent commit
![local git repository](https://blog.udemy.com/wp-content/uploads/2015/08/image036.png)

