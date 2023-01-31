+++
title = "Part I: The Thing about the Leaving Certificate..."
description = "I'm reflective...pensive mode...I commit introspective acts "
date = "2023-01-29"
author = "Leon Reilly"
categories = [
    "Reflection",
    "Effortposts",
]
tags = [
    "Leaving Certificate",
    "School",
]
toc = false
draft = false

+++

### I. 

So I’m going to write about the Leaving Certificate (LC), and what it’s like to experience the culture that surrounds it. 

When I was 13, I attended a talk. It was called something like "A 625 Student's Guide to English"<cite>[^1]</cite>. I don't have any older siblings and didn't (at the time) have older friends who I could collapse into, asking them endless questions, so it was incredibly useful. As you can imagine, pretty much all the content in that talk was new to me. *"English has two papers??!! Nahhh, ain't no way..."* English was, and still is, one of the most challenging (statistically, anyway) exams to score an H1 in<cite>[^2]</cite>. Having a benchmark to measure my work against gave me some direction for the next six years. 

Looking back now, it was definitely a bit odd that I attended that talk. I was 13. I had just started secondary school. I would be sitting the LC in 6 years; why did I need to listen to a talk about the LC now? Part of the answer is that the culture surrounding the LC is weird. There's an obsession with it. It’s a little weird all the way through school. Partly, I think it's because it was temporally defined for you. "June, six years from now", and each year that went by you'd count down by one. I distinctly remember thinking that I'd be in school sitting exams in a few years, instead of enjoying the sun. It's quite rare to know the date of an event that will (significantly?) affect the trajectory of your life. I doubt most people know what date they'll become parents, or what date they'll buy a home. But there’s a special weirdness when you’re 17 and begin studying your LC subjects. There’s a sudden flush of perspective that wasn’t there before—*this is important; this matters*. Those news articles about the LC that your eyes would previously glaze over when reading, you now read a bit more closely. Platitudes people tell each other bounced off the hallways and locker rooms: they’re going to “get serious” and go to the library. I felt that the arc of people's lives was bending towards discipline and studiousness. Perhaps, growing up had offered them a gestalt shift on what each of them valued. 

Another part of the weirdness manifested itself as strategy, which began to feature in subject choices. Everyone was aware of the H1 and H2 rates for each subject—everyone wanted to maximise their total points by seriously considering subjects that were statistically the most "easy". In retrospect now that I've done some exploratory data analysis, perhaps we shouldn't have been choosing subjects based on overall H1 and H2 rates, but the H1 and H2 rates by gender...

<iframe title="Male vs Female Subject Grade Distribution, 2019" aria-label="Range Plot" id="datawrapper-chart-6EK3C" src="https://datawrapper.dwcdn.net/6EK3C/2/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="2013" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();
</script>

I promise we'll get back to discussing the LC, but first I want to talk about this graph. All subjects appear to roughly follow a normal distribution between the 8 grades. Very cool. There is also, more importantly, a very obvious gap in achievement between boys and girls. One interesting observation my friend pointed out is that, in Ireland, many secondary schools are segregated by sex. About a third overall are single-sex. They're unusually common. This gives us quite a large sample size to test how strong the effect of attending a single-sex school has on achievement. By how much would the needle move if you attended a mixed school? And in what direction? Does it matter what your gender is? While the literature about the benefits of single-sex schools is mixed, my sense is that the achievement gap would narrow.

Yet, what is most interesting to me is, despite the lead girls have in almost every subject, some STEM subjects still lag behind. Most notably, in Mathematics. I suspect the reason why the gap is so large in Maths, compared to other STEM subjects, is because Maths is not really optional. As in, many university courses require you to achieve a minimum grade in Maths and, if you take Higher Level (HL) Maths, you automatically get 25 bonus points—that's a pretty good reason to take it, even if you're not great with numbers. However, these incentives are equally true for boys, so perhaps the gap in achievement reflects differences in mathematical aptitude or confidence in their abilities for a given exam year<cite>[^3]</cite>. What about Ordinary Level? While it appears that boys and girls seem to take HL at similar rates (65% vs 62%, respectively), we can interrogate this more rigorously. Here is the count data:

| Grade Level    | No. Female | No. Male  |
|----------------|--------|-------|
| Higher Level   | 8830   | 9323  |
| Ordinary Level | 16358  | 15116 | 

We can perform a chi-squared test for independence to check if there is any association between gender and course level. We get a chi-squared statistic of 51.1 and a p-value of < 0.00001, so there is a statistically significant difference in the take up of HL and OL between boys and girls. To get a sense of how large the difference is, we can look at the Pearson residuals from the chi-squared test.

| Grade Level    | Pearson Resid. Female    | Pearson Resid. Male      |
|----------------|-----------|-----------|
| Higher Level   | -4.00 | 4.06  |
| Ordinary Level | 3.03  | -3.08 |

To interpret these values, we need to consider both the magnitude and the sign of the residuals. A positive residual means that the actual data is higher than what we would expect if there was no relationship. The opposite is true for a negative residual. The larger the absolute value of the residual, the more significant the difference. For example, the residual for the HL course for female students is -4, which indicates that the observed count (actual number) of female students taking the HL course is 4 standard deviations lower than the expected count (what we'd expect if there was no relationship). So, there is a significant difference in the take up of HL Maths between male and female students.

In other stem subjects like Physics or Chemistry, the achievement gap narrows or reverses, as girls who are good at those subjects self-select into them. I'm particularly interested in the achievement gap in STEM subjects for girls in mixed and single-sex schools. I've heard some compelling arguments explaining why girls in single-sex schools perform better in STEM subjects<cite>[^4]</cite>. 



[^3]: In the book Good Economics for Hard Times, they mention this study: Steven J. Spencer, Claude M. Steele, Diane M. Quinn, Stereotype Threat and Women's Math Performance,Journal of Experimental Social Psychology, Volume 35, Issue 1, 1999, Pages 4-28. I'm just speculating, but perhaps some amount of self-reinforcing discrimination is going on. 

### II.

Every year there are complaints that the LC relies too much on memorisation and that it needs to point itself towards continuous assessment. To a certain extent, I think this critique is true. Many subjects, like Biology, simply require you to memorise a large amount of information. A shift is probably welcome in those subjects. Additionally, there is no effective way to hedge against having a bad day when 100% of your grade is determined by one exam. 

> Levels of stress were high among sixth year students, particularly among girls. Just under 40 per cent of females reported ‘losing sleep with worry’ and over 50 per cent felt ‘constantly under strain or pressure’. </p>
> — ERSI, Student Stress and the Leaving Certificate (2015)

It's worth pointing out that, while many LC subjects can involve vast, *cruel* amounts of memorisation, this belief that every subject is just a matter of memorisation can also inform how students tackle subjects like Maths or English. It also informs what supports parents and students believe they should lean on. Given how competitive and—for many, stressful—the LC is, it can be quite easy to shred money trying to get an advantage. But, I think many of the modalities that people use to get a leg up in the LC are, all things considered, not all that helpful. Having gone through the entire process, I’m just going to offer some thoughts on the different approaches some use. 


[^1]: The girl who gave the talk was excellent at English. I think she got something like 99.75% in her English exam. Obviously, to get a score that high takes a bit of luck, but the point is that she was pretty good. 625 for 625/625 possible points in the LC.
[^2]: Before the pandemic arrived and changed the grade distributions, in 2019 about 2.9% of students got an H1, which is the lowest of all LC subjects. Take a look at the graph to get a better sense. The LC is graded from a H1 (best) to a H8 (worst). The "H" means "Higher Level" and "1" means you achieved >90%. A H2 means you scored >= 80% but <90%, and so on.
[^4]: The basic argument is that in single-sex schools girls feel more comfortable taking STEM subjects. 




### III.

The practice of buying notes as a method to do better in LC exams is bunk. As in: you didn’t make them yourself, and they’re usually not particularly helpful. There are some caveats to this, which I’ll talk about in more detail. 

**You didn’t make them**: Depending on who you are, I think making your own notes can be a useful exercise. I am very sceptical of relying on someone else’s notes as a tool to revise or even learn the material for the LC. As I flagged earlier, many LC subjects place a large focus on how much you've remembered. Ergo, buying notes for a subject like Biology or Physics doesn't make much sense because all of the information is already in your textbook—you're just paying for someone who has just rewritten the whole thing in their own words. Maybe they've even *generously* thrown in some exam questions too. Buying someone else’s notes who has (hopefully) done the hard work of making the notes themselves isn't going to make life all that much easier.


**Not Useful**: There is an argument that textbooks have too much material that isn't relevant to the exam. Notes tell you "what you need to know"<cite>[^5]</cite>. I don't buy this argument because textbooks are also written with the exam in mind—there isn't much waffle. I also don't buy it because I've seen far too many notes that rewrite the textbook. I was given some notes for Physics that were purchased from a (popular?) website that sells notes for a variety of subjects. The notes are [almost identical](https://youtu.be/31GRu9OYuVM) to the text in my Physics textbook. Nearly word for word. All that's happened is that the textbook has been packaged into a pretty LaTeX pdf. Similarly, I've found the notes for English from Grind Schools that have been passed down to me are also not particularly helpful. They do not offer unique insights into poems or plays that your teacher doesn't know. They just point out the themes and general ideas. Perhaps all of this is just a symptom of teaching to the middle of the class...

[^5]: I attended the open day of a grind school and they said the same thing. While all open days have some performative aspect to them, this particular open day felt like I was watching a paid actor perform what a [super-ultra-hyper-mega-meta](https://youtu.be/1Wpwbs4bhaY) energetic and dedicated teacher would probably be like. I think it was supposed to impress the students and parents. 



What is the caveat I have? It’s for English. It is a very specific caveat because I do not think you should buy notes for English—I just don't think they're worth it. I think you need to get your hands on an H1 essay, ideally a tour-de-force essay. This is because textbooks for poetry and Shakespeare usually do a poor—sometimes no—job explaining how to think about or analyse poems and plays. The sample essays are also a bit cringe. So are most of the essays that you can find online.

From talking to my friends at other schools, it can be quite difficult to actually see a tour-de-force essay. Some teachers seem to be quite fond of handing out sample essays that got an H3 or H2. This is not particularly useful. Even if you are not aiming to get an H1, surely seeing an H1 essay will still be more valuable than an H2 essay...


<iframe title="Top 6 Subjects by Candidates, Grades Achieved" aria-label="Grouped Column Chart" id="datawrapper-chart-MANJm" src="https://datawrapper.dwcdn.net/MANJm/2/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="400" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();
</script>


Let me talk a little bit about poetry in particular. Often what notes will give is a summary or explanation of the poem. Sometimes, they will point out features of the poem or techniques that were used. There is little depth beyond this, that is, there is no consideration for why the technique was used etc. In my experience, the best points you can make about a particular poem will be the ones you find yourself by carefully combing through the poem. Sometimes the internet can help—usually, if you browse Google Scholar for long enough, someone will make an interesting observation about the poem. Sometimes, the internet won't help. That's why you need to carefully think about your poems and develop your own insights. Sure, everyone will spot the use of imagery. Everyone will spot the use of rhyme. What you need to do for a higher grade is to discuss techniques and features most other students won't talk about and talk intelligently about them. This is hard work, and it takes a lot of time. But you'll have analysis or points almost nobody else will have—and might you even surprise your examiner with your lucid insights. 

All things considered, I think if you want to achieve an H1 in English you need to do much of the work yourself—work that buying notes will not do for you, work that grinds will only do to a limited extent. 



### IV.

Writing about private schools in Ireland could be its own entire article<cite>[^6]</cite>. I'm not going to discuss whether private schools should exist or not. The most unusual aspect is that private schools in Ireland are not really private. They're closer to public schools that charge fees to attend. Fees are low compared to private schools in the UK, Canada, the US, or elsewhere (approx. €5,000 rather than €50,000 a year) as a result of the state paying for the salaries of (most of) the teachers who work in private schools. 

[^6]: (Disclaimer: I went to a private school) As you can imagine there are two sides to this question. One side wants to stop the state from subsidising private schools. The other side wants them to continue. The argument for cutting state funding is pretty straightforward—it's not fair for the state to be subsidising the education of the wealthy. The strongest arguments I've heard for continuing to subsidise them are that: **A)** Most private schools are Protestant, and many Protestant parents value being able to send their children to a school that promotes their religion. If the state stopped funding private schools, their children would have to go to public schools, which are usually Catholic, or they would have to pay significantly more to send their children to a private school. **B)** The state actually saves money by funding these schools. Parents who send their children to private schools are taxed by the state (to pay for the education of others) and pay the fees charged by the school. It is an odd situation.


Among some immigrant communities (and maybe more widely in Irish society?), there is a strong interest in attending private schools, if possible. I know of families who have put their children down on a school's waiting list at a very young age. I'm not sure if this obsession is justified—at least, in Ireland anyway. 

To be clear, I'm not claiming that attending a private school doesn't have any benefits. It certainly does. However, I think many overestimate the real benefit of attending these schools when it comes to exam results. There may be other valid reasons parents may want to send their children to a private school, but I suspect the main reason is academics, as private schools tend to feature at the top of the league tables<cite>[^7]</cite>.

[^7]: League Tables are also a poor reason to select a certain school. School isn't all about exam results!!! The proxy league tables use for academic performance is 3rd level progression rate. Except, if you're trying to distinguish between the schools at the top of the table, it's not very helpful. It may be significantly easier for schools near Limerick or Cork to have a higher progression rate as the Universities there have lower points requirements compared to universities in Dublin. If you want to distinguish between schools in Dublin, seeing how many students went to attend a particular University is not useful either—it gives no indication of what courses those students chose. Ideally, schools would publish their mean and stdev values for their LC points. [Except, it's actually ILLEGAL to make a league table based on exam results.](https://www.irishstatutebook.ie/eli/1998/act/51/section/53/enacted/en/html#sec53) This is interesting to me—I wonder if the reasons why this specific law was made are equally true of the existing League Tables, for example, additional stress placed on students etc.

The fees that parents pay mainly buy their children a certain milieu. Bar a few very large private schools, attending a private school doesn't guarantee better facilities. Attending a private school also doesn't guarantee better teachers. My sense is that the presence of private schools at the top of the "League Table" rankings reflects the parental background and income of these students more than the particular school they attended. For example, the Irish-speaking schools Colaiste Eoin and Colaiste Iosagain usually rank at or near the top of the league tables and are both public schools. However, the schools are located in an affluent area and the parents who teach their children Irish and then send them to an Irish medium school likely place an emphasis on education.

Anyway, all this is to say that attending a private school may not be the boost parents—especially new immigrants who might make large sacrifices—might expect it to be. Out of all the variables that influence a student's academic performance, I would not expect attending a private school to have a large coefficient—in Ireland, anyway. Of course, I might be wrong about all this.

### V.

There are endless amounts of advice on how to do well in your LC on the internet, so I won't say too much about this. By far, the most important component is how much work you do yourself. So, what should you do to maximise your points?


- **StudyClix**. Buy StudyClix and get the best package you can afford. Alternatively, you could try to convince someone else to give you access to their account. From my own experience, this is a far better use of your time and money instead of completing the physical past papers that Edco sell. This is because you can do targeted practice and rigorously interrogate every single question on a topic, and be prepared for any 'surprise' questions they might ask. This was invaluable to me for Physics (Particle Physics in particular) and Applied Maths. 

Anyway, here I am six years later after attending that talk and writing my own version of "A 625 Student's Guide to the Leaving Certificate"<cite>[^8]</cite>. Maybe it's a little poetic. Maybe it's a bit sad. But what would I know. 




[^8]: Probably something closer to "A 825 Student's Guide To All The Nonsense and Bullshit People Will Tell You about The Leaving Certificate".









