---
layout: post
title: "Building a website with React"
date: 2021-01-02
---

I spent the end of 2020 with an uncharacteristically large amount of spare time on my hands. Due to the ongoing global pandemic, my winter break involved stroking my 
foster kitty, Kido, with one hand, and tacklilng other personal projects on my laptop with the other. In this post, I'm going to talk about using React to build a
simple one page site for an upcoming McGill AI conference we are organising. 
This is the second time I am using React to build a site. The first time was over the summer of 2020, in preparation for our hackathon, MAIS Hacks - I had no idea what I 
was doing. I relied heavily on the repo and code created by the previous year's team. That website can still be seen at maishacks.com.
In October, I joined Earth Hero as a volunteer web developer. Their website is built with React and gatsby (although the people who spend more time maintaining and updating
that website are web dev wizards with lots of experience and knowledge) and allowed me to continue familiarising myself with things. 

As such, I felt somewhat more comfortable tackling this next website. I'm using this post to walk through the steps and considerations taken as a note to my future self, in case
I need to come back to things. I'll note that my understanding of this topic was picked up mostly by reading other people's code, scouring the internet for solutions to my 
problems, and trying stuff out. It might not be the best way to do things or even the correct way to do things, but this is where I'm at as of now. When I learn how to 
do something better, I will write a blog post to explain that. 

## Getting started

React is a javaScript library for building user interfaces. It's efficient because it automatically updates and renders components as you change and build things. 
It's well documented and widely used, so there are lots of more formal resources to get you started. However, if you're like me and prefer to just dive straight in, here's
how to get started. You'll need to have ```Node>=8.10 and npm >= 5.6``` on your machine.
Then, from the command line, run:
```
npx create-react-app name-of-app
cd name-of-app
npm start
```
(where name-of-app stands in for the name of your project / project folder ). 
```npm``` may be replaced by ```yarn```, however I don't recommend mixing the two. Pick one for a project and stick to it. Otherwise, this could mess up certain 
packages and other files that are part of your project making it a nightmare to run or commit things later. Also make sure you're always using the most updated version of ```npx```.


## The Outline

Cool! ```http://localhost:3000/``` should now be running the app. The basic files from ```create-react-app``` should display the React logo, with a message to edit 'src/App.js'
if you want to make changes. The directory name-of-app will be structured as follows:
```
name-of-app
├── README.md
├── node_modules
├── package.json
├── .gitignore
├── public
│   ├── favicon.ico
│   ├── index.html
│   └── manifest.json
└── src
    ├── App.css
    ├── App.js
    ├── App.test.js
    ├── index.css
    ├── index.js
    ├── logo.svg
    └── serviceWorker.js
    └── setupTests.js
```
At this point, I had a vague idea of what I wanted the finised product to look like. When it comes to hackathons and conference sites, the layouts all tend to be quite
similar. They're all made up of a single page containing a navigation bar, a landing page (the home page), a footer, and a series of other sections like 'About' and 'FAQ'.
They also have certain graphic design elements that were kindly provided to me by the McGill AI graphics whiz. 

I like to set everything up to get an overarching view of everything that needs to be filled in. You can organise your files however works best. Some projects
have a folder for all their Components, and a separate one for Styles and Modules etc. Some people don't use folders at all. I like creating a seperate folder for
each of my Components in my src folder. For the Conference site, this is what that looked like:

```
src
 ├── landing
 │     └── Landing.js
 ├── about
 │     └── About.js
 ├── speakers
 │     └── Speaker.js
 ├── fair
 │     └── Fair.js
 ├── schedule
 │     └── Schedule.js
 ├── faq
 │     └── FAQ.js
 ├── sponsors
 │     └── Sponsors.js
 ├── footer
 │     └── Footer.js
 ├── App.css
 ├── App.js
 ├── App.test.js
 ├── index.css
 ├── index.js
 ├── logo.svg
 └── serviceWorker.js
 └── setupTests.js
```
This allows me to directly place any images or assets into the relevant Component folder. 

The other thing also worth setting up is the file for your css. This can go in the public folder as follows:
```
public
  ├── css
  │     └── layout.css 
  ├── favicon.ico
  ├── index.html
  └── manifest.json
```
Then add the following line of code to 'index.html' somewhere under `<head>`:
```html
<link rel="stylesheet" href = "%PUBLIC_URL%/css/layout.css"/>
```
Cool! We're pretty much set up. 

A fun thing to do at this point would also be to change the `favicon.ico` in the public folder. This image determines what appears
in browser tab when you open the website. Use any online converter to transform your image into a favicon.ico (don't rename it!) and
replace the existing React logo image in the folder.

## The Landing

Generally, the components share the same layout. They begin with import statements, followed by any constants or styled elements. Then
the Component is rendered and exported.
```JavaScript
import React, {Component} from 'react';

class Landing extends Component{
  render()  {
    return (
      <header id="home"
        <nav id="nav-wrap">
         <a className="mobile-btn" href="#nav-wrap" title="Show navigation">Show navigation</a>
	       <a className="mobile-btn" href="#home" title="Hide navigation">Hide navigation</a>
         <img className="nav-logo" src={logo} alt="mais logo"/>
         <ul id="nav" className="nav">
            <li className="current"><a className="smoothscroll" href="#home">Home</a></li>
         </ul>
       </nav>
        ....
      </header>
    );
  }
}
export default Landing;
```

         








  



