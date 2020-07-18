---
layout: post
title:      "Javascript/Rails project"
date:       2020-07-18 23:46:55 +0000
permalink:  javascript_rails_project
---


I'm glad I was able to get the project done on time but I wished I could've done more. Life got in the way and I had to focus my attention elsewhere. Still, I'm proud of what I have done. This project was really, really tricky though. I spent more time rearranging code than actually creating it. Some lines wouldn't work until after the page load, so I would stare at my screen for hours wondering why my event listeners would only work in the console(google chrome). Ugh!!!!

Despite being frustrated and wanting to fling my laptop against the wall, I enjoyed working with object-orientation. I avoid working it through my project because I had trouble understanding why it was needed. I can manipulate the objects in a function and be done with them without creating classes. However, after talking to my cohort lead, I realized its importance. Here are two classes that I made for my project.


 ```
 class Category{
    constructor(cat){
        this.id = cat.id 
        this.name = cat.name
    }

    renderCat(){
        return `
        <button id="${this.name}" data-id = "${this.id}">${this.name}</button>`
    }
}



class Chocolate{
    constructor(coco){
        this.id = coco.id
        this.title = coco.title
        this.price = coco.price
        this.product_details = coco.product_details
        this.quanity = coco.quanity
        this.img_url = coco.img_url
        this.category = coco.category 

    }
    renderChocolate(){
    return `<div class="chocolate-card" data-id="${this.id}">
    <img data-id="${this.id}" src="${this.img_url}"/>
    <div class="container" >
    <h2>${this.title}</h2>
    <p>Price per box: $${this.price}</p>
    <p>In Stock: ${this.quanity}</p>
    <p data-category="${this.category.id}">${this.category.name}</p>
     </div>
    </div>`
    }
}
 
 ```
 
This makes my code way easier to read and manage. If I needed to change something in renderChocolate, all of the instances that uses this method would be affected. This is good because I don't have to check every instance because they all use the same method. 

