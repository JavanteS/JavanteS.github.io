---
layout: post
title:      "First Project"
date:       2020-04-17 16:50:45 +0000
permalink:  first_project
---


Wow...I can't believe I created my first CLI gem. I was stressing out on Sunday because I didn't know where to start. There were a lot of APIs to look at and I'm so glad they were complied in a list on GitHub. I knew what I wanted, which was Anime, but the whole project just seemed so daunting. I didn't even have my local environment established yet. 

![](https://media.giphy.com/media/C8YQmifxpHZG8/giphy.gifhttp://)

After asking for help and learning how to set up my local environment, the whole project didn't seem so scary. ~~Well, it was for a little, because I entered my password incorrectly in Ubuntu and it was a bit of trouble trying to fix it. Don't do what I did.~~I decided that I wanted to use the Ghibli' films for my project, I loved the studio's films growing up and I was so happy that there was an API for it. With my local environment set up and an idea in mind, I was eager to get started.  

While I was coding, I thought "Wow, this is pretty fun.". I created my class "Movie" which makes(initiates?) movie objects. Each object is initialized with name, description, year(release date), and a rating score. This information is pulled from the API. Then I thought to myself, maybe the user will like to know more about the director(s), so I decided to add that.

So, I thought everything was going well until...I hit the loops. I always had a hard time understanding them so I asked for help. I didn't want any user get stuck in looping purgatory, so I had to use "gets" to avoid that. This ask the user for their input and ,from what I gathered, pauses the looping. I had use "case" before because it makes my code looks so clean and pretty but I decided to switch to "while". I hardly ever use "while" and this was the perfect time to use it. After using it, I was starting to understanding how it works. 

```
while input != "exit" do
            
            if input == "films"
                prompt_two
                list_movies
        
            elsif input.to_i > 0  && input.to_i <= Movie.all.length
             
                  movie = Movie.find_info_by_number(input)
                  list_info(movie)
             
            
            else 
                puts ""
                puts "Sorry, invalid entry.  Please, try again"
            
            end
                puts ""
                puts "Pick a number to read the movie's description. To see the list of films again, type 'films'. Type 'exit' to leave."
                input = gets.strip.downcase
        end
         puts "Goodbye!"
```
Yay!

As I was working, I would show my progess to my family. When I was just setting up my class and the API, I got so excited when I saw my objects were initialized with just a name. While they didn't share my excitement entirely, I'm glad that they were willing to test out my project. It helped me catch a lot of errors, typos and all. This project was really fun and I can't see wait to see what the next one will be like. 



