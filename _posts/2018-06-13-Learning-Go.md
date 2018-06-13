---
layout: post
title: Learning Go. Day one.
---

## Why start a blog

My reasoning for starting this blog was to document the journey through learning Go.

Yesterday's blog consisted of me getting up and running and building the website itself. This was quite simple thanks to [barryclark](https://github.com/barryclark/jekyll-now).

## The purpose

I aim to learn [Go](https://golang.org/). With the aspiration of building a framework and deploying it with some sort of containerisation.

## Why?

I have heard about Go a few times now, from blogs, or a talk by the guys at [Monzo](https://monzo.com/) here in Belfast or from the blurb over at the [golang website](https://golang.org/).

>Go is an open source programming language that makes it easy to build simple, reliable, and efficient software.

Which I think is very appealing. I've heard good things about the compiler and I have read blogs on how you can benchmark performance quite easily. I'm quite excited to be able to test this for myself.

## Where do I start

My first port of call if someone mentions a language that I am not familiar with is [Learn X in Y minutes](https://learnxinyminutes.com/docs/go/). So this is what I did.

This explains the basics from comments;
```go
// Single line comment
/* Multi-
 line comment */
 ```

to starting a Web Server;
```go
func requestServer() {
    resp, err := http.Get("http://localhost:8080")
    fmt.Println(err)
    defer resp.Body.Close()
    body, err := ioutil.ReadAll(resp.Body)
    fmt.Printf("\nWebserver said: `%s`", string(body))
}
```

A simple google search will bring you to the [tour](https://tour.golang.org/welcome/1) of the "golang" but this isn't very thorough. I can understand how it would be good if you are a beginner to programming which makes it accessible.

I will begin [here](https://golang.org/doc/install) in order to get myself up and running.