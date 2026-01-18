This post is going to be about the use of statistics in the Letby case, focusing on the chart, which is not the only statistical issue with the case, but the one this post talks about. I think a lot of the objections to the statisticians points are not valid and their critiques are not fully understood.

First of all I will start out by pointing out that the fact that during the trial and indeed even on subs like this that discussing the trial statistics gets far less mention than medical and other matters doesn't mean these things are more important, the amount of time spent on something is not an indication of the strength of that piece of evidence. Indeed the chart is the most important piece of evidence offered by the prosecution by a mile. The medical evidence doesn't point to anyone in particular, and the other purportedly incriminating evidence of Letby of Facebook searches, attempts to place her cotside in some of the cases but not all, "confession note", "document fraud" etc is laughably weak, none of it adds up to proof. So without it, there isn't a case to answer. Even if you don't agree with this, the statistics still merits some analysis as it clearly was part of the case.

First of all I will deal with what you might call the "naive" statistics, without looking at the clinical picture of the babies can tell us which is what I think some seem to think is the only concern of statisticians.

Different areas of statistics could be used to establish there is evidence of a crime, the "spike" along with its decline, which was discussed by Prof O'Quilgley in [The Telegraph](https://web.archive.org/web/20240831151848/https://www.telegraph.co.uk/news/2024/08/31/lucy-letby-spike-baby-deaths-explicable/) and in his [draft paper](https://osf.io/nk9da), pointing out that is not a statistically significant result. So the fact that Letby left the unit at a similar time is neither here nor there, the spike itself is not even remotely suspicious, so if the end of it coincided with her removal doesn't matter, an argument you still occasionally here. An invalid criticism that could be made is that this is quite what the "spike" is not quite the right "spike", if the data was classified in a different way then you might get a more significant spike this is not valid. This is just the Texas sharpshooter fallacy, you need to come up with the criteria in a neutral manner for the results to be valid, not look at the data and then start to reclassify in an attempt of p-hacking, for example you might find if you take rather than a calendar year you "draw the target" around June to June, the CoCH "spike" might be a more significant result, but this would plainly be cheating.

One claim you hear about this data is that somehow his analysis is invalid as it looks at all deaths born at a hospital rather than ones that die on the NNU. This is another Texas sharpshooter fallacy. A "spike" in the proportion of deaths taking place at the NNU, but no broader "spike" does not provide evidence of a crime, a hypothesis here could be the unit is taking on sicker babies or problems with the transport network, but it doesn't provide evidence of foul play.  Additionally the implausible idea that there was on a "spike" in babies were being killed that were transferred in from elsewhere, but not ones born there has never seriously been suggested.

So no evidence of a crime here.

The 2nd one worth having a look at is Letby's shift pattern and that she is "always there" both when babies collapse but survive and when they die, we have data from the inquiry and the trial that shows during the indictment period,[ she was on duty for 10 out of 13 deaths.](https://thirlwall.public-inquiry.uk/evidence/inq0010072-sheet-1-of-table-from-the-countess-of-chester-hospital-mapping-staff-members-on-duty/) We don't know exactly how many she was on duty for the period before this but we do have from her cross exam (From CS2CR) a good idea:

>Well, how many infant deaths had you witnessed in your employment before Child A?

>**Not many, maybe two or three at the Countess** and then several more of my placements at Liverpool Women's.

>Two more at Liverpool Women's?

>You say several more, I'm offering an alternative of two more.

>I can't say. I don't keep track of numbers.

>I'm just going off what you said to the police, you see.

While we can't be sure this is true, if it was false you would expect Johnson would have challenged her on this, and we have to assume its true if no other evidence to the contrary has been offered yet by anyone. Additionally, it is not really plausible she went on a killing spree before 2015 given the lack of any rise in death rate before this, further corroborating this claim (another area we could analyse more rigorously but I will leave this for now).

Side note: I know this is just number of deaths witnessed, not number on duty, but it seems implausible that she would have been on duty for a death but completely ignored what was going on.

[We know from the inquiry she started in January 2012.](https://thirlwall.public-inquiry.uk/transcript/14-10-2024-transcript-of-week-6-day-1/)

>**Nurse ZC:** Letby and I commenced our employment on the NNU together on the same day in January 2012

[We also have data that from 2012-2014 there were 8 neonatal deaths.](https://www.bbc.com/news/uk-england-merseyside-38901317) (another source [here](https://thirlwall.public-inquiry.uk/wp-content/uploads/thirlwall-evidence/INQ0002837_2,3.pdf))

So taking the 3 number of deaths on duty for pre-2015, assuming again quite pessimistically that she is there for a quarter of the time, using a binomial, which assumes independence which could be questioned, no adjustment for night shifts etc, the point I'm making is this really is the worst case scenario:

B(13 + 8, 0.25)

P(X >= (10+3)) = 0.04% or around 1 in 2500.

Lets just take that year as well:

B(13, 0.25)

P(X>=10) = 0.01% or around 1 in 10,000.

What can we say from this? At best we can say Letby is an unlucky nurse, but you would expect in thousands of nurses to get a nurse that is this unlucky, to infer evidence of a crime from this would be what has been called a "Lottery Fallacy". Nor the fact she might have been moved from night to day shifts affect this analysis, as we make no assumption about time of day of the shifts. So there is no evidence of a crime here.

For "collapses" data is harder to find and nobody seems to have collected the data on this by looking through all 400 babies that have go through the unit each year, or even done a random sampling, and I talked about Liverpool Women's Hospital in a previous post. [What we do have however a review of babies transferred out](https://thirlwall.public-inquiry.uk/wp-content/uploads/thirlwall-evidence/INQ0005336_06_07.pdf) (Its worth reading the whole email here):

>Attached is the health record review that Anne Martyn and I undertook of infants who collapsed/deteriorated in our NNU and needed transfer elsewhere from June 15 - July 16. Anne and I initially looked at a larger group of patients who required transfer out during that time period (can't remember exactly how many — perhaps 30 or more).  
\[....\]  
When we finished the review, Anne gave the notes she had made to one of the senior nurses (I think it was Sian Williams), and we had understood that, with the help of colleagues in HR, there would be an analysis of all the nurses and doctors on duty when each patient deteriorated/collapsed (not just the nurses assigned to the patient for that shift, although that info would clearly also be included).

[The results however seem to have been disappointing for the consultants:](https://thirlwall.public-inquiry.uk/wp-content/uploads/thirlwall-evidence/INQ0014268_01-02.pdf)

>The review Anne Martyn and I undertook. Ian didn't tell me how many patients had been identified but said there were quite a few (I don't think he was hiding anything, he didn't have the data with him), but he's promised to send me the info.

>**Apparently, Lucy did not feature prominently in the staff correlation analysis of those collapses.**

>\[I'm keen to see the data because if there really were many such cases, then I'm not sure that these were the specific ones that were highlighted as being unusual or unexpected. If the staff analysis was undertaken for too many of the collapses, that might have obscured an unusual correlation between certain staff and those unusual/unexpected collapses. Let's wait until we've seen the data; Ian agreed that I could share it with all of 'us.'\]

So again no evidence of a crime here and its unlikely that a bigger sample size of collapses would lead to an correlation, when the smaller one didn't. The only real possibility is maybe she attacked them in a way that didn't lead to any of them being transferred, but I haven't really heard any kind plausible theory like this, and this is just speculative witch hunting absent any data.

I'm sure this is obvious to all but putting together things that are not evidence of a crime can't magically become evidence either.

[The one other source here is Dr Evans "data", but its so clearly fake its not worth considering.](https://www.telegraph.co.uk/news/2024/12/08/baby-deaths-were-30-times-higher-under-letbys-care/)

He appears to have said there were 15 "deaths or collapses" when Letby was on duty. But **only 2 in the entire year** when she was not on duty, this is so absurd its not even worth considering, contradicted even by his own evidence at the trial and the inquiry.

>Dr Evans, a retired paediatrician from Carmarthen, said he believed statistics “played no role in the prosecution case” but said he had gone over the shift data and found that 9.2 per cent of Letby’s shifts involved a death or collapse compared to 0.3 per cent for other staff.  
\[...\]  
Dr Evans said he had found that there were 15 deaths during Letby’s 163 shifts, compared to two deaths during the 635 shifts when she was not on duty.

So he gets 15/163 = 9.2% for Letby of events on shift and 2/635 = 0.3% for not on shift. Not credible or serious claims. Granted its hard to know exactly how he fudged the data, but a reasonable guess can be made.

We know there were 17 deaths (presumably these are 17 events he has selected), but 4 of them happened after transfer elsewhere so for them he counts 'on duty' as on duty at some point they were on the unit.

For the ones on the unit he appears to have done the trick of fudging 'on duty' to actually mean on duty or on duty the shift before (see [the spreadsheet ](https://thirlwall.public-inquiry.uk/evidence/inq0010072-sheet-1-of-table-from-the-countess-of-chester-hospital-mapping-staff-members-on-duty/)from the inquiry).

As Gibbs hints at in the email above, it seems then after this given the statistical evidence gathered didn't support their claims, they then want to go hunting for statistical evidence by adjusting for the nature of the collapses, which to be fair isn't entirely unreasonable (although if there is *no correlation at all* then adjusting for more factors is unlikely to help). This is where they seem to go next with the police investigation.

# Were statistics used at the trial?

Now we have talked about "naive" statistics can tell us, we can now look at what the data says when purportedly adjusting for the clinical picture, like the prosecution did at the trial. Here is a key piece of statistical evidence offered at the trial (the original version):

First of all some remarks about the nature of the chart, some have claimed that the chart is not statistical evidence, it is just crime scene reconstruction. Including it seems [Dr Evans himself](https://www.youtube.com/watch?v=xqPVx3M7SRM):

>I did three interviews with Rachel Aviv and her colleague, and her article is very, very skewed. It makes a deal deal of the statistics. Statistics had no role at all in the prosecution case they simply presented information in a spreadsheet simply to prove that the defendant was present at the scene of the crime, which is the first thing that any prosecution has to do.

First of all this is clearly nonsense, if they just wanted to show Letby was on duty for the events she was charged for that required only one column, the other nurses didn't matter. To be fair I think he means its to show the defendant was at the scene of the crime and other nurses weren't. However this explanation doesn't make sense either for the following reasons:

* On duty doesn't show you were at the scene of the alleged crime, nor does being off duty show you weren't. If they wanted to take this approach they could have just come up with a crime scene reconstruction of where the prosecution say where each person was when, with evidence and then the defence could challenge that evidence. Granted there is some discussion of this at the trial, but the spreadsheet adds nothing new to that debate, so using it for this purpose and this purpose only is just prejudicial and would have been tossed out by any sensible judge. This argument was actually used by the prosecution at the trial and Letby correctly points out it is invalid:

>Do you agree that if certain combinations of these children were attacked, then unless there was more than one person attacking them, you have to be the attacker?

>No.

>You don't agree?

>No, I've not attacked any children.

>I understand your case. You are saying you haven't done anything, right? But if the jury concluded a certain combination of children were actually attacked by someone, then the shift pattern gives the answer as to who the attacker was, doesn't it?

>No, I don't agree.

>You don't agree? Why don't you agree?

>Because just because I was on shift doesn't mean I've done anything.

>No, but it would follow that if, let's say, I'll use numbers, all right? I won't refer to specific cases. Let's say if baby 5, 8, 10, and 12 were all attacked, if the jury looks at the medical evidence and says they were all attacked by someone and you're the only common feature, it would have to be, wouldn't it, that you're the attacker?

>That's for them to decide.

>Well, of course it is. Of course it is. But as a principle, do you agree with that?

>No, I don't feel I can answer that.

* There is no reason to limit the investigation to just neonatal nurses (or doctors), everyone working at the hospital or who was there at the time has to be suspect if a crime was committed there but not known by who.
* Note the chart sums up the total at the bottom, there would be no reason to do this if its only purpose was to help reconstruct the crime scene.
* For the chart to only be useful in the way suggested, you would need to be sure that a crime took place if not in all the cases then at least some of them (see below the prosecution are only willing to go as far as to say for they have done this for 3 of them), its doubtful if they have done this.
* "Statistics had no role at all in the prosecution case" seems to have never been mentioned by the prosecutor themselves, who seems to suggest the opposite.

Here are some samples of the prosecution using such stats arguments, both the[ "spike" argument](https://x.com/LucyLetbyTrials/status/1872789503993364646/photo/1) mentioned above:

>Prior to January 2015, the statistics for the mortality of the babies in the neonatal unit at the Countess of Chester Hospital were comparable to other like units. However, over the next 18 months or so, there was a significant rise in the number of babies who were dying and in the number of serious catastrophic collapses. And this rise was noticed by the consultants working at the Countess of Chester and they searched for a cause.

This is a bit misleading, while it was performing poorly in 2015, it was comparable to other units of its type. But I suppose this could be read either way.

And also with claiming that Letby was the only nurse when 'suspicious incidents' happened, for which the only evidence given is the chart it seems, which is supposed to chart all them. The words 'coincidence' is referenced 44 times in his closing speech, but just to show one important example (Again [from CS2CR](https://www.youtube.com/watch?v=5_-VSF451wc)):

>But the insulin proves that somebody was trying to kill children, as does the case of Child O. And it shows—all of those cases show—the awful lengths to which that person was prepared to go. I say 'that person,' ladies and gentlemen, because the similarities between many of these cases do show you, don't they, that it was a single person sabotaging children. **And the coincidence of the presence of Lucy Letby on all these occasions shows who that person was.**

Put simply (putting aside the slightly dubious assertion the incidents are similar), the prosecution say the cases of insulin cases and O establish a 'smoking gun' that a crime has been committed, and the stats of presence for 'suspicious incidents' show who has done it, the "Chain link proof". Perhaps disturbingly similar to previous nurse miscarriage of justice cases, but of course the strength of the argument is fact specific to each case. Like other nurse miscarriage of justice cases some other weak evidence is offered that is claimed to incriminate for example handover sheets and the "confession note" but even the prosecutor downplays them, e.g:

>Although I say this, the notes are only part of the story; there are more critical aspects to this case.

# What can the chart show?

First of all let us point out what is in no doubt whatsoever, no statistician would defend just eyeballing the chart as a good way of of analysing the data, as was what was done a the trial: this is someone's life, the integrity of the justice system, all the people's lives affected by this case and the future of the NHS at stake we really should expect better. Just to go over one example [Prof Green said](https://www.telegraph.co.uk/news/2024/07/09/lucy-letby-serial-killer-or-miscarriage-justice-victim/): “The spreadsheet duty roster is almost a textbook example which I would give to my students of how not to collect and present data.”

However just because the data wasn't presented in an ideal way doesn't mean the conviction is unsafe automatically, so we need to analyse it more carefully. If such an analysis does show it doesn't in fact establish the claim made by the prosecution, then I think all the convictions are unsafe given how central the chart is to the case as I explained above.

The first part of this we are going to take the chart at face value and ask what it says, later on we will ask if the chart is what it says it is and expand on Prof O'Quigley's argument that it might be a fake.

There are 2 things the chart could be used for in the case either:

* To establish that a crime has been committed.
* To establish who the culprit was.

This gets to the heart of what is difficult about Healthcare Serial Killer cases, its often pretty hard to establish if a crime was committed at all, medical diagnosis are not perfect and have an error rate especially based medical notes year later that are an incomplete picture of what happened, even if you accept the diagnoses of insulin poisoning, air embolism etc its still hard to prove that it was done with intent rather than a mistake. Even clinical tests have much higher false positive rates than forensic tests making this type of evidence difficult as well. Witnesses and motive are normally nonexistent as well. You might still be able to prove it but in this post I'm not talking about the strength of the medical evidence, so for the sake of argument I'm going to analyse the chart based on various levels of strength the medical evidence could be:

* In all cases we have proof of a crime. This seems to be quite close to Dr Evans's position, but he tends to back down from the extreme form of this when pushed.
* We have proof that a crime has been committed, not necessarily in every case on the chart (or even none of them individually, we are just sure that *some of them* are) but want to use the chart of 'suspicious events' to show who the culprit must be. This one seems to be the prosecution's case.
* We don't know if a crime took place at all and want to use the chart of 'suspicious' but not proven cases to establish the statistical unlikelihood that no crime took place. Arguably this was sort of the defence's position at the trial (perhaps damaged by Letby saying somebody poisoned the baby with insulin and its not a mistake from the unit), there is no proof of a crime and the prosecution presented no valid statistical evidence or alternatively [Cannings](https://www.bailii.org/cgi-bin/format.cgi?doc=/ew/cases/EWCA/Crim/2004/1.html) suggests a case shouldn't be built purely on statistics so there's is no case to answer.

For technical reasons reasons I'm not going to get into here the Beta-binomial distribution is the correct one to use for this, I'm not going to do any model validation as Prof O'Quigley has already done this. I'm going to use his parameters of Beta(2.92, 16.23) as well.

So looking at the first example what are the chances of a nurse being present for 24 incident? I will spare you the calculations that don't look good on Reddit anyway:

P(X = 24) = 10\^-9 approx

Astronomically low, but again this isn't the probability of guilt, you wouldn't want to fall for the prosecutor's fallacy. To avoid this lets come up with a prior probability that Letby is guilty. Given we have established a crime has been committed, lets say we have no idea who it might be to start with and lets be generous and say 100 suspects, if you include all the doctor's, nurses, cleaning staff etc. Another generous assumption that there is Letby is no more or less likely than anyone else in our prior, we get a prior probability of guilt of 1%.

Given P(G) = 0.01, P(E∣G) = 1 and P(E | not G) = P(X = 24)

P(not G | E) = 10\^-7 approx

Bang to rights then, as I'm sure will surprise nobody. But there are serious problems with this, we assumed that there are no other factors that could explain the correlation other than she is the culprit, but is that really true? Some alternatives are:

* Somebody else is trying to set her up, the pure stats can't tell us if this is a reasonable possibility.
* Maybe she worked more shifts than the others, the Beta-binomial model to oversimplify a bit assumes she is on shift for about 15% of the time, which an underestimate. So already the prosecution has hit a hurdle, the prosecution rests on a false assumption (I think she worked long hours was mentioned at the trial.), or at the very least the idea maybe she works longer hours than the others is a reasonable doubt.

Strictly speaking, this is the end of the road for the prosecution's use of the chart, by the evidence presented in court, we have proven any results from the chart are not valid as it doesn't adjust for working hours.

Granted its not that simple, in some of the cases if you accept there is a crime, given the circumstances its at least arguable she is the only possible culprit (but none are really 100% on this). Also in practice I'm if you adjust for her working hours the calculations won't come out good for her, but its arguable jurors are not supposed to speculate like this, they should only focus on the evidence in front of them.

There is actually a further problem here, even if we have proven the chances are that she did one of them, how do we know which ones? Granted this isn't that hard if we believe that medical serial killers are rare, the chance of 2 (or more) of them is remote, [according to this paper around 1 in a million](https://journals.sagepub.com/doi/abs/10.1177/096853329500100404). (I will spare you the calculations here), so therefore she very likely did all of them. But even this is tenuous, the 1 in a million number is just the number convicted (rightly or wrongly).  So even here there are questions, given the relative rarity evidence wasn't presented in court, presumably it was felt that medical serial killers are extremely rare is just common sense (its not).

But hold on, there is a problem here, we know in some of the cases on the chart (Like Child B, possibly C, D, G, I, J, K, N) she has an alibi. Granted the alibi in every case can be doubted, maybe the witness was wrong who give her it for example, but are we to believe that its wrong in all cases? If not then given we have taken as a premise that all 24 are crimes, then it follows the must be another attacker around, regardless of the low base rates. Once we accept there is an another attacker on the unit, the idea that she might have been set up by that attacker is a possibility.

So ***even if*** we accept for the sake of argument all the cases on the chart 100% crimes, it still can't be used to prove Letby is the culprit. Maybe its not quite as easy as [the prosecution say](https://www.bbc.com/news/uk-england-merseyside-63201201):

>Mr Johnson said: "If you look at the table overall the picture is, we say, self-evidently obvious. It's a process of elimination.

Anyway moving on from this one as I don't think anyone really believes that all 24 cases are proven in isolation are crimes, there are no stab wounds etc, and of course its a fantasy to think if they were all 24 were proven attacks, nobody would have noticed this at the time, until some genius "expert" witnesses come along to prove this. Medical diagnosis of course has a certain error rate (Dr Evans himself keeps changing his mind) and regardless even if you accept say the air embolism theory wholesale, this doesn't prove it was deliberate in all cases.

One way on analysing this is we know that some of the events on the charts are crimes but not all, how many do we need to be sure of her guilt?

First of all the other entries on the chart are not relevant here, and the slightly academic problem of not knowing her working hours in the earlier case becomes even worse here. So we can't really say anything about the chances from the chart itself. Nor can we for the case of where we don't know if a crime has taken place at all.

Maybe we can come up with some common sense numbers about how much the maximum time she would be on shift to see if we can still build a case against her, but the chart doesn't help here. This is probably for another post.