---
layout: post
title: F# vs C# - Downloading a Web page
---

How do the languages compare when downloading a Web page?

# First look

The first look on the [downloading a web page tutorial](https://fsharpforfunandprofit.com/posts/fvsc-download/) explains the F# code as I have uploaded [here](https://github.com/ConnorDickson/LearningF-/blob/master/Interactive%20Examples/downloadingAWebPage.fsx). My first impressions are that it looks simple and comparable to C# but instead of the *using* keyword there is just *use*. I would expect this to behave in the same way. After reading the explanation  of the code this is the case.

# Testing interactively

I ran the example and was quite impressed. After studying the code I like the callback feature and can see how this would improve code reuse and writing generic functions. We now have a "fetchUrl" method that can be used in many different ways, we just happened to choose to print out the first 1000 characters of the response to google.

# Baking in parameters

Being able to create a second fetch function that always uses the "myCallback" function is very impressive. My brain is always trying to compare this to what I know, which is C#, so in the last line of the baking in parameters example we have;

```F#
// test with a list of sites
let sites = ["http://www.bing.com";
             "http://www.google.com";
             "http://www.yahoo.com"]

// process each site in the list
sites |> List.map fetchUrl2
```

Which I know I could implement with link within a method call easily but with F# it just seems cleaner. I also know that I could *bake in parameters* by setting a default within a method in C# or creating a new method that just calls the method with a hardcoded value but again these solutions don't seem as clean as the F# equivalent.

Reading the C# implementation that uses callbacks after reading into F# has made me want to Func's more when I am writing C#.