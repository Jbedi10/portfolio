## Grade Reflection

# What Grade Did You Earn? I believe that I earned an A- in STA 518.

# How Did You Demonstrate That Grade? 
So for our grades, the course objectives is what we are to base our argument on. The reason I believe I earned an A- in this class would be based on the following:

Import, manage, and clean data: This one is pretty straight forward as i was able to import the results.csv. In the load phase I did get rid of all NA although I did not believe there were to be any, but this is one thing i like to make sure I do before any analysis is started. Also in my graph code chunks I use groupby, filter and summarise to manage data and extract the data I need. I do believe my understanding of this course objective is very good. This section came natural to me and I was able to learn rather quickly. I think I aced this part of the course objectives. I was not caught up by anything and learned the rules and parameters of functions very easily! (few examples below!)
## Load Data

```{r echo = FALSE}
stats = read.csv("~/STA 518/Final Project/Portfolio/Final Proposal/Final Draft Portfolio/results.csv")
head(stats)
str(stats)
stats[is.na(stats)] = 0
summary(stats)
results = read.csv("~/STA 518/Final Project/Portfolio/Final Proposal/Final Draft Portfolio/results.csv")
head(results)
str(results)
summary(results)
```
```{r echo = FALSE, fig.align = 'default', warning = FALSE, fig.width=30, fig.height=30, fig.cap="Results by Season"}
results %>%
  group_by(result, season) %>%
  count() %>%
```
```
tot_home_goals = results %>%
  group_by(season) %>%
  summarise(total_home_goals = sum(home_goals)) %>%
```
Create graphical displays and numerical summaries of data for exploratory analysis and presentations.
This was one of the coolest thing I think I will take away from this class. I am assuming there are A TON of different ways to display data, however, ggplot was awesome to explore. There are so many cool things you can do to make data easy to read. As I stated earlier, people are visual. And I do believe that if I was tasked with graphing data, I would be able to make really easy to read graphs with GG plot. I believe I was able to create graphs that are not 'easy to make' as I was able to change dimensions, sizing, fills, text size, colors, landscape. I was able to get pretty detailed and dove pretty deep into being able to change graphs to what I thought looked best. I do believe atleast for ggplot I aced this objective in the course. Here are a few examples of graphs I was able to create in my project! I do believe that I could have gone further with graphing. However, for my first R class I do believe I was able to demonstrate my ability of graphing in the project. However, for my last graph I wasnt able to figure out the best way to finish it. I think I got carried away with trying to make things look cooler rather than graphing the data in a readable way. I wanted to show the difference of home and away wins between Manchester United and Manchester City. But I think my googling got a bit out of hand. Unfortunately had to turn in the project this evening and I wasnt able to finish. However, I will go back and finish as I want to create a distill page for this to show my Manchester United fans just how bads its been for the past years for their club lol!

This is probably the coolest graph I made. I was able to create two seperate graphs one for home wins and one for away wins. After that I merged the two and created a master. Total wins both home and away from 2006-2018. This probably took me like 3 hours to figure out and it finnaly compiled for me and I dont think I have ever been so happy.
```
ggplot(overall_wins, aes(x=reorder(factor(Team), wins), y=wins, fill = wins)) + 
  geom_bar(stat = "identity", position = "dodge") + 
  xlab("Team") + 
  ylab("Wins") + 
  theme(legend.position ='none',axis.title.y = element_text(size=50), axis.text.y = element_text(size = 25), axis.title.x = element_text(size=50),axis.text.x = element_text(angle = 90, size = 25), plot.title = element_text(size=50, hjust = 0.5)) +
  scale_fill_gradientn(name = '',colours = rev(brewer.pal(10,'Spectral'))) +
  geom_text(aes(label = wins), hjust = -0.3, size = 10.5) +
  ggtitle("Number of Overall wins in the English Premier League from 2006/07 to 2017/18") +
  coord_flip()
```

Write R programs for simulations from probability models and randomization-based experiments: Welp, here we are.. the course objective that I was not able to complete. To be quite honest I have no idea how to do this or even where to start. This is the reason why I believe I did not earn a full A or A+ . I wish I was able to say on my reflection that I earned the full A, but I have no idea where to start with this or anything along those lines. Im hoping you understand that I just do not know how to do it. I could have tried, but like I said I didnt even know where to start. 

Use source documentation and other resources to troubleshoot and extend R programs.
Write clear, efficient, and well-documented R programs.

I do believe that my code is effiecient or as effiecient as it can be.. and it is readable. So I believe that this part of the course objective was completed. Sometimes I feel like I am writting too much / taking too many steps to get to where I want to be. But sometimes it helps me work things out and get to the final code correctly. When I jump corners thats when I start to run into errors. However, I do feel my code is easy to follow and easy to read!

Anything else?: 
Well to be completely honest I believe I did my best to learn the material at a high level. Obviously some things are harder to grasp than others, but I feel like I put my best foot forward in this class to make something that I can relate to. I will be able to create more analysis with this type of format now that I know what to do. I believe as an aspiring data employee I have learned about some things I may have never looked into before. This will only help me continue to grow and be an important employee for my future employer. I am very greatful for this class set up as I believe it allowed me to create my own type of project and show who I am. I do work hard in school, but its always nice to have those classes that you dont have to stress about (too much atleast.) I feel I do learn better with a structured lecture, but this was eye opening as it allows students to depict their actions and not have streamlined outcomes!

