---
layout: post
title:      "Sinatra Project"
date:       2020-05-15 00:49:09 +0000
permalink:  sinatra_project
---


I really, really liked working on this project. In the beginning, I was freaking out(as usual), because I had trouble understanding CRUD and how they flow together in a controller. It didn't click until I hit lab a that went over all the routes. 
![](https://media.giphy.com/media/cNwYCZjq9fOQAwmcPi/giphy.gif)

The big Fwitter lab also helped me understand the routes a bit more. So, when it was time to start building the project, I had a lot of fun time doing it. For some strange reason, I loved using the helper methods. 

```
helpers do
      def logged_in?
        !!session[:user_id]
      end
  
      def current_user
        @user ||= User.find(session[:user_id]) if logged_in?
      end
    end

```

The code in these methods is pretty short anyway, but still, they save time and typing. I can use `logged_in?` to make sure any users that are not logged in can only view certain pages and vice versa. This protects my views from any harmful attempts to break my code. `current_user` was also pretty handy because I didn't want any users editing content that wasn't theirs.  When used together, they worked beautifully.

See?

```
delete "/games/:id" do 
        if logged_in?
          @game = current_user.games.find_by_id(params[:id])
          if @game 
            @game.delete
            redirect "/games"
          end 
        else
          redirect "/login"
        end    
      end

```

It is simple and I appreciate that. 


