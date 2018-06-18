---
layout: post
title: Starting go development
---

Figuring out what I can do with golang

## Start from the beginning
The link I said I was going to begin with previously [here](https://golang.org/doc/code.html) gives an example of how to layout your project. I have just created a [repo](https://github.com/ConnorDickson/LearningGo) where I will store my example code that I am learning but I had created it using the same structure mentioned in the guide mentioned. The src folder is where all go projects will exist, but they will have their own repositories, but they will all build to the same bin folder. This seems strange to me that there is almost a connection between all your projects, but they exist independently from one another unless you explicitly link them. It seems like it would be difficult to have the projects live in separate places on disk. 

Now that we have the folder structure sorted I wanted to get stuck into learning how to build a go project beyond the hello world example I executed previously to confirm my environment was configured correctly. 

A cool benefit of having the one place for all built executables is that you can add that folder to your path environment and then if you run _go install_ you can then just type the name of your program in a cmd prompt and it will run. I wonder if we can find out the current folder this command was run in and perform an action in here. I could write a utility that perform actions depending on where you type the command. This will be my first project. 

## Finding the current path the command was executed in
I want to be able to perform an action on files depending on where we run the command. First, I will need to write to the console the current path;

Turns out that is very easy as there was a question answered [here](https://stackoverflow.com/questions/18537257/how-to-get-the-directory-of-the-currently-running-file) and this is the code;
```go
import (
    "fmt"
    "log"
    "os"
    "path/filepath"
)

func main() {
    dir, err := filepath.Abs(filepath.Dir(os.Args[0]))
    if err != nil {
            log.Fatal(err)
    }
    fmt.Println(dir)
}
```

and this is some example output from [this](https://github.com/ConnorDickson/LearningGo/blob/master/CurrentPath/CurrentPath.go) file

>C:\Users\ConnorDickson\go\src\LearningGo\CurrentPath>CurrentPath
>
>C:\Users\ConnorDickson\go\src\LearningGo\CurrentPath
>
>C:\Users\ConnorDickson\go\src\LearningGo\CurrentPath>cd C:\
>
>C:\>currentpath
>
>C:\

## Iterating the files in this directory
Combining the knowledge learnt from the previous go file and the answer from [here](https://stackoverflow.com/questions/14668850/list-directory-in-go) I produced [this](https://github.com/ConnorDickson/LearningGo/blob/master/IterateFiles/IterateFiles.go)
```go
package main

import (
	"fmt"
	"io/ioutil"
	"log"
	"os"
	"path/filepath"
)

func main() {
	dir, directoryErr := filepath.Abs(filepath.Dir(os.Args[0]))
	files, filesError := ioutil.ReadDir(dir)
	if directoryErr != nil {
		log.Fatal(directoryErr)
	}

	if filesError != nil {
		log.Fatal(filesError)
	}

	for _, f := range files {
		fmt.Println(f.Name())
	}
}
```

Which replicates the functionality of _dir_ and lists all the directories and files wherever you run the command. 

I am happy with having setup a repository to play with and gaining an understanding of a bit more to do with go. I will carry on with this example when I write the next blog entry.