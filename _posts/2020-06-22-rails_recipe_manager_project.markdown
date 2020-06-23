---
layout: post
title:      "Rails Recipe Manager Project"
date:       2020-06-23 02:39:17 +0000
permalink:  rails_recipe_manager_project
---


This project was really something else.  I had a rough time trying to get my nested routes do what they were supposed to do. When I finally got a route to work, another route that was working before stopped working.

![](https://media.giphy.com/media/MlNSich1jeAzm/giphy.gif)


When that ordeal was finally over, it was time to refactor some code. It was highly recommended that we mustn't repeat ourselves when we code, so I decided to put this code 

```
@recipe = current_user.recipes.find_by(id: params[:id])
```

into a method. I noticed that I repeated this line throughout my recipes controller, so I stuffed it into method in the bottom of my controller(under private methods) and place the method in a before action. Like so...

```

before_action :set_recipe, only: [:edit, :update, :destroy]

```

My edit, update, destroy actions will be the ones that use this method, so I deleted the "@recipe=..." line from each action. I did not set this for show because it is not the same like my other actions. 

```
def show
        if params[:category_id]
            @recipes = current_user.categories.find(params[:category_id]).recipes

            @recipe = @recipes.find_by(id: params[:id])

            is_it_a_recipe(@recipe) 
        else
            @recipe = current_user.recipes.find_by(id: params[:id])

            is_it_a_recipe(@recipe)
        end
    end
		
		```
		
"is_it_a_recipe " is another private method I created that checks for valid recipes and will redirect the user if none are found. It is also a safeguard in case a user tries to change the url (recipe's id) to something that doesn't exist (yet) and thus breaking my views. I really like the private methods because it saves me time from typing repetive code which I have a habit of. However, this action has some beefy ~~and slightly repetitive~~ code still, and I will have to condense this something more manageable. 

