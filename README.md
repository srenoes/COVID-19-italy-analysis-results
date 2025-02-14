# COVID-19-regional-data-analysis-SIR

#Intro

This is a model page that tries to find out questions about the near future states of COVID 19 on the basis of regional data.
Simulation data is used to answer that question. Even though the mathematical model looks very complicated the stuff behind it is very easy to understand. This SIR model is about people that can still get infected(S), people that are infected (I), and those that are removed(R), or those who got it and recovered (lets hope) or are dead.

Key aspect in this model and in other related models is a number called basic reproductive number or R0. And that number represents the number of people that are infected on average by one infected person. Math with this number is fairly easy to understand. An R0 of 2 will give 2,4,8,16,32 infected persons or the amount of infected is doubling! each time it is transmitted. And and R0 of 1 will give 1,1,1,1,1. And R0 of 1 will thus not increase the number of infected, and for R0<1 it goes down e.g. R0=1/2 --> 1/2,!/4,!/8,1/16  aso. The trick that now everybody is hoping for is to get this number as low as possible, if by any means possible then clearly below 1. 

Also very important is that the number of peak infected persons will be much lower with an R0 close to 1. This is not very much mentioned anywhere. And I dont know why. In official figures it always looks like the peak will be much broader but not very much smaller. But actually, the higher the infection rate can be suppressed, this peak will get really small as well and probably the ultimate goal to reach with discipline. 
Why do I mention this? Well because I got the impression that people might believe they'll get it anyway. Well no absolutely not! Not, if every infected infects less than 1 person now. Maybe very optimistic perspective but I think not unrealistic at all. And data below supports this argument. 

Just to give some numbers for an R0 of 2 I think it was 4-5% who will top have it at the same time, or when you go out you could count until 20 and  you meet somebody who is infected. Very scary as a whole. Not the world end though if you get it, unless you are a little older.

Now as it looks like for Bergamo those numbers are still very low, compared to the scary 5% we might get to if R0 does not decrease. And we dont want to go there believe me. Thus stay at home if possible. It shouldnt be difficult to get R0 down to half I would think but if R0 is 2 or 1 makes really actually a huge difference! Eazy again to understand what means 2x2x2x2x2x2x2x2x2 oe 1x1x1x1x1x1x1 not to talk about 3 or 4 putting in such a row. This seems was typical for the start in every country. See more numbers here: https://cmmid.github.io/topics/covid19/current-patterns-transmission/global-time-varying-transmission.html

Aditionally, and about that nobody is talking about, a reduced R0, if close enough to 1 will also significantly reduce the amount of people that will get it. So its not only about that the peak is spread out, nope. It is ALSO TINY COMPARED TO the peak you get when R0 is 2 for example. Continue to look at the pictures. And think about R0 and what is means because it is so easy

Another thing is that obviously at some stage the people that can get infected will run out. Meaning then it will not be possible to infect more people than 1 on average. But of course this will only be the case when a lot of people will have got it already. And then we are in scary numbers again. For R0 close to 1 this happens much earlier, or it is always theoreticlly possible to suppress R0 below one. And no matter what this means we have the case of reducing numbers !/2 1/4 1/8. Eazy. right? 

How to get the exact numbers from data is another question. But as it should be clear now that if we have an R0 of 4 then we need to put the number of infections down by 4 to get an R0 of 1. now 4 is quite extreme as it seems. And even then it shouldnt be impossible. Look at China. What they did. And also look at Italy data. This doesnt either look like were into crazy numbers yet. But maybe you shouldnt buy a dog to be able to move around.

Example figure (succesfull fitting + extrapolation): Version 1503

![Bergamo fitting results_1503](SIR_fitresults/15032020/Italy_SIR_fit_000_Bergamo.png)


This now unfortunately looks completely different with data from 1603T

![Bergamo fitting results_1603](SIR_fitresults/16032020/Italy_SIR_fit_000_Bergamo.png)

And now it starts to look different again. However, now only last 7 days' data are fitted (19.03.2020). Lets hope this is true.
Fingers crossed. Although this looks like there could be a little relief in the not too far future, there is no time to rest.
As you can see only 1%-2% of the total population would  be infected, and the infections probably went down due to strict measures. Anyhow if this is not handled carefully the epedemia even then could restart on the remaining 98%!! Maybe thats why they said 40-60% will get it. But I think better you fear too much than too little. Be careful wherever you are.

Data from 19.03.2020
![Bergamo fitting results_1903](SIR_fitresults/19032020/Italy_SIR_fit_000_Bergamo.png)

New data 22.03.2020
![Bergamo fitting results_2103](SIR_fitresults/22032020/Italy_SIR_fit_000_Bergamo.png)



And some figure I created with geopandas showing the wave that went down italy from north to south:

![Italy animated map until 150320](Italy_animated_map.gif)


#Technical description


Data Analysis results with model fitting based on as local as possible data (best data is Italian officials province based data).

Mostly ODE based modelling and parameter fitting, but also other local results







I changed the name of the repo because it made sense.

The question I currently have is how big is R0 typically, because that is somehow unclear to everybody.
However, the italian dataset in some case fits so nicely with a SIR model including all data that you can hardly ignore that

But on the other hand if you include only last 7 days for example for Bergamo it will fit to R0=2 and humangous increase compared to the latter, where we are already beyond point of inflection.

Another question that runs around my head is that policiy in europe now is to delay instead of prevent infections sort of. I am a bit wondering why they think that the peak will not change, because I would have thought so that lowering the infection probabilities beta will always lower the amount of people that will get it in the end.



Very much interested also to suggestions relating to gamma. As this one should not change that much, whereas beta will be heavily affected by measures applied by the countries. 

Otherwise stay strong and at home and do some hell modelling  and publish and discuss.
As you can see this topic is very complicated and not only because of the model being nonlinear, but also the data
I resorted to fitting beta and gamma, but rather S0 or I0 should be included in the fitting as well

Also if somebody has insights into how to appropriately weight the data fitting with time series for prediction that would be great to know.

(I can only imagine that weights could be iteratively changed to minimize confidence bands) but obviously beta changes with time. And hopefully for the lower. LETS at least HALF BETA! I know we can do it! (by staying home). And then this prkl CORONA will DIE!! 

WATCH OUT FOR INFLECTION POINTS IN THE CUM DATA




#what I intend to do (but please join me if you want)
Generall I'll share pictures and code and data respective data scripts to merge different available sets

in the results directory are pictures I took as a snapshot from the analysis.

There is one big json file which includes the plot data.
All the other sav files are generated by lmfit (https://lmfit.github.io/lmfit-py/intro.html).
lmfit method used to save the fitting results was save_modelresult, fitresults can be loaded with load_modelresult

The json also contains the name of the saved .sav files

The code for the model function you see directly above.


Look at the wiki for more information about model and more



