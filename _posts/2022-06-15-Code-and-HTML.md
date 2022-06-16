---
title: Writing Block Codes on HTML
date: 2022-06-15 20:01
---

<!-- markdownlint-disable -->

I'm still learning my way through HTML, markdown files, & CSS. Currently I have all of this in a container center-aligned and changed the paragraph tag `<p>` to justify the body of the posts.
My previous post I tried to give an example of the interface concepts in the Go language but the output was not how I expected. So let's try this again:

<pre>
<code class="language-go">	
type human interface{
	speak()
}

type person struct{
	name string
	age int
}

func (p person) speak(){

	fmt.Println(`I am the dragon reborn 
			and in madness I shall soon prevail`)
}

type superHuman struct{
	person person
	powers []string
}

func (sh superHuman) speak(){
	fmt.Println("I am god amongst men")		
}

func (h human) saySomething(){
	h.speak()
}		
</code>
</pre>

Hopefully this works when I upload this. This is done through VIM "como dios manda" I have been spoiled using VSCODE and auto-complete. Next would be adding pictures!

Yours,

Jose R
