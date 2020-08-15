---
layout: post
title:      "Final Project Fun Javascript React Redux"
date:       2020-08-15 20:38:42 +0000
permalink:  final_project_fun_javascript_react_redux
---


I had a lot of fun with this project. There were basic requirements for this one so I had a chance to go a little wild. I'm so proud of my finished product. I recall being so anxious and scared when I started my first project(CLI gem), and now I'm not freaking out over the small stuff. While I'm feeling more confident in my coding skills, I'm a little sad. I'm going to miss my cohort and my cohort leader. I didn't talk much but I enjoy seeing the funny comments my classmates made in the slack channel. 

![](https://media.giphy.com/media/l22ysLe54hZP0wubek/giphy.gif)

Enough sad stuff, let's get to the coding! I was cleaning up my code then remembered I need 5 stateless components per project requirements. This was easy to do but I had to do some rearranging to get my handle clicks to work.  Stateless components don't have state and so I had to change this 

```
class Meal extends Component {

handClick=(event)=>{
     this.props.deleteMeal(even.target.id)
		 
		 }
		 
		 render(){
		 return (
		 <div className="container">
                            <div className="row">
                                <div className="col-sm">
                                {this.props.meal.category}
                                </div>
                            <div className="col-sm">
                                {this.props.meal.name}
                            </div>
                            <div className="col-sm">
                                {this.props.meal.date}
                            </div>
                            <div className="col-sm">
                                {this.props.meal.calories} calories<button id={this.props.meal.id} onClick=     {this.handleClick}>X</button>
                            </div>
                        </div>
                        
                    </div>
		 )
		 }
}
```

to this ...(stateless)

```
const Meal = props=>
                        <div className="container">
                            <div className="row">
                                <div className="col-sm">
                                {props.meal.category}
                                </div>
                            <div className="col-sm">
                                {props.meal.name}
                            </div>
                            <div className="col-sm">
                                {props.meal.date}
                            </div>
                            <div className="col-sm">
                                {props.meal.calories} calories<button id={props.meal.id} onClick={props.handleClick}>X</button>
                            </div>
                        </div>
                        
                    </div>

```

I love how clean it is and all it is doing to rendering the info on the page. HandleClick didn't disappear but is passed in as a prop from my container. I had to figure out which component is going to do the heavy lifting and I handed that the job to my container. My stateless component is not tracking changing data as I have other components that will handle that.
