+++
title = "Charcoal, Human Trafficking, and Machine Learning"
description = "Discussion of what I did over the summer"
date = "2024-09-16"
author = "Leon Reilly"
categories = [
    "Reflection",
    "Effortposts",
]
toc = false
draft = false
+++

### Preface

The research I worked on is sensitive. For straightforward reasons, I'm leaving out details and results that can't be shared publically. Here's the final slide deck of our presentation.
* <a href="/Users/leonreilly/Documents/GitHub/LGRblog/content/resources/DSSG Final Presentation.pdf" download>DSSG Final Presentation 2024</a>

### I. 

Here's some context for what I worked on this summer. In Brazil’s forests, a curious structure repeats itself every so often: parallel lines of circular structures with black mounds lying in front of them. Each circular structure is a kiln used to transform wood into charcoal. They are the telltale signs of charcoal production kilns. Here's a Google Earth image of what one looks like.


<img src="/DSSG.png" alt="lake" width= "800">


Over the past decade, Brazil has been one of the world’s leading producers of crude steel.[^1] In 2023 it was the ninth largest producer of crude steel in the world. In 2022 it was the largest producer of charcoal in the world—fuel to feed the steel industry. Yet, the process of producing charcoal is typically intertwined with violence and exploitative labor. This is partly a consequence of the dangerous and illegal nature of the work. I think it's relatively straightforward to see why—chucking wood into these suffocatingly hot kilns and trying not to choke on the fumes seems pretty awful. Since 1995, about 2,830 people have been rescued from what Brazilian authorities define as slavery-like conditions. And it’s worth pointing out that illegal charcoal production has been difficult to combat since the work is typically done in remote locations and the sites operate for a finite amount of time. 

The Stanford Human Trafficking Data Lab and Brazilian Federal Labor Prosecution Office are collaborating to use a remote detection tool called CHAR to locate charcoal sites quickly and accurately. The Human Trafficking Data Lab developed a computer vision model trained on low-resolution, high-frequency satellite imagery to accurately identify and pinpoint zones where forced labor is likely used to produce charcoal. Human post-processing is then used to select sites for task force site inspection. The technology allows for a “more proactive anti-trafficking intervention, moving beyond merely reactive, tip-driven initiatives.”

[^1]: World Steel Association: [Annual Production Data 2023](https://worldsteel.org/data/annual-production-steel-data/?ind=P1_crude_steel_total_pub/BRA)

```
Satellite Imagery ➔ CHAR ➔ Manual Processing ➔ Brazilian Task Force
```

The major wrinkle with the existing model is its high rate of false positives, confusing roads, rivers and other visually similar features to the two parallel lines that are distinctive of charcoal kilns. As a consequence human post-processing often involves looking at images that cannot be charcoal sites due to their location, e.g. being in the ocean, on a highway, etc. Successful improvements over the current manual labeling would speed up task force prioritisation and therefore the potential to improve high-level anti-trafficking outcomes, that is, workers rescued. To this end, our project developed a downstream Gradient Boosting Classifier model trained on appropriately selected geospatial and survey data to augment the upstreams model’s accuracy.

### II.

I think there's a few modalities from which you can look at the task we set ourselves. The intuition behind using geospatial data is that there is some signal in the data since there are presumably various important considerations that the people who set up the charcoal sites have to make. On one hand, you might want to construct a charcoal production site near a road since you ultimately are transporting the charcoal on trucks to be burned somewhere else. On the other hand, maybe you might not want the site too close to the road since that increases the risk you are discovered. Equally, for other features like waterbodies, you might make similar arguments re the quality of the soil/vegetation that might incentivise a charcoal producer to locate further/closer to a waterbody. The goal was to prioritise developing an interpretable model rather than a black box model since that would probably be more useful for the taskforce in Brazil. There might also be some second/third order effects that our geospatial features are proxying for, but our main goal was to generate as many potentially salient geospatial as possible and then think about removing some and seeing if they improved the model's performance. So, what variables did we end up with at the end of this process?


