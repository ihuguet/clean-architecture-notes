Personal opinion: Blindly applying clean architecture everywhere all the time will end with an overengineered project, for sure. Moreover, many things are assuming a really huge project developed by many different teams, which is not the case for many projects.

Response copied from: https://www.reddit.com/r/csharp/comments/17wvvfm/comment/k9k4xrc/

> I find the most important question at the start of a project is: "Has anyone written something like this before?" Moving mountains to hire someone who can say "yes" will often pay off a lot more than any books you read.
> 
> What we do is HARD. The people who write articles and books may have experience or they may not, but if they do they're writing about the ideals that worked for projects they did. Even if you are doing the same kind of project, there could be thousands of tiny differences in your environment that make some of their good decisions bad for you.
> 
> You aren't supposed to be making your project's diagrams look like theirs. You're supposed to be treating architecture like design patterns and asking:
> 
> - What are the problems this approach is trying to solve?
>     
> - When is it most effective at solving those problems?
>     
> - When is it least effective?
>     
> - What complexity does it add?
>     
> 
> Architecture always trades one kind of complexity for another. It's "good" when we agree the complexity it creates is somehow "better" than the complexity it is addressing. It's "bad" if we can't agree there's a benefit or that the new complexity makes it worse.
> 
> Tools like AutoMapper have one job. They do that one job well. They work the best if you warp your project design to suit that one job. What I consistently find in the complaints about it is people have identified dozens of _adjacent_ jobs they wish AutoMapper could do and try to use it for those. Or they don't want to design their project the way it intends, so they try to adapt it. This is like carving out part of a hammer so you can use it as the blade of a screwdriver: it's bad at the new job and you've made it worse at its original purpose.
> 
> Most of the time when I see someone having trouble with a textbook architecture or process, it's not the architecture or the process that has failed. It's that they've blindly followed the textbook without asking if it's appropriate for their case. They follow processes to the letter and treat friction as something to get used to instead of a sign that something is wrong.
> 
> It's why people hate Scrum. It's why they hate Kanban. It's why they hate unit testing. It's why they hate SOLID. Salesmen pitch these things as silver bullets and that if you just follow an easy process your projects will improve. These are _ideas_ and _theories_ you have to analyze and critique, comparing them to your own experiences and asking if your problems and their problems align. Some domains never have the problems that require these things. Others have complexity that is impossible to manage without them.
> 
> I feel like you're stumbling into why I don't like "example" projects for architecture. They're not _real_ problems. They weren't created by people who had a customer with vague requirements approach them. They weren't created by companies trying to predict the needs of customers. They didn't grow organically over years as their maintainers grew more familiar with what users wanted. They're produced by looking at a diagram and writing code that adheres to it.
> 
> It's kind of like how we can tell the difference between a painting in a museum and a finished page from a coloring book. Even if the person who filled in the coloring page is exceptionally talented at staying within the lines, their creativity is limited and we usually don't find the finished work as impressive.
> 
> They're meant for people to spend an hour of study to get the idea of how the moving parts of that design approach work. That usually means they lack real complexity. If the author finds a sticky problem that requires a hack, they simply omit that feature because they don't want to mar the example with a side discussion.
> 
> Real projects have warts. They don't have perfect symmetry. They have weird places where a hack exists because some third-party integration veered from the standard. Architecture books can't directly account for those, but we can often use design patterns and abstractions to "hide" them from the rest of the code.
> 
> That doesn't mean architecture is bad. But like how people complain fashion models set poor expectations and standards for beauty, example architecture projects usually present a very false view of reality.
>
> - Slypenslyde (Reddit user)

