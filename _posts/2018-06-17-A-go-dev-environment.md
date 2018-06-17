---
layout: post
title: A go development environment
---

Start developing with golang

## Step one, download Go
As I said in my previous post I will begin [here](https://golang.org/doc/install). This was very painless, they then have a "Test your installation" section, what I found strange is the use of environment variables everywhere. It seems that if you don't use the defaults for the installation and your workspace you need to set them manually. I wonder why they are used at all. I created my workspace and followed the hello world example.

I am using VS Code as my IDE, once I created my first go file, hello.go, it recommended I install the go extension, which I did.

I now have this code;
```go
package main

import "fmt"

func main() {
	fmt.Printf("hello, world\n");
}
```

I then ran _go build_ in VS Code but I got an error that go was not recognised as a cmdlet. If I run _go version_ outside of VS Code it works okay. I couldn't work out what the problem was but after restarting my PC the command started to work inside Visual Studio Code. So, I am unsure of what the problem was, but it's fixed now. The extension also prompted me to update it because I had changed one of the Environment Variables for Go.

So now after running _go build_ I have an exe. After running _go install_ it was installed into the bin directory. I then ran _go clean_ and it was gone. 

I still don't quite understand the layout of the directory and what happens if I want to run multiple projects. I also don't quite understand the purpose of all the environment variables, but I am now able to develop my first proper application.

I feel like [this "How to Write Go Code" documentation](https://golang.org/doc/code.html) will answer some of my questions so that's where I will start next time.