---
title: 'What makes AI, "Intelligent"?'
summary: 2025 marks a pivotal year for artificial intelligence. With advancements accelerating at an unprecedented pace, we stand on the brink of an AI revolution that promises to reshape industries, redefine human-machine interaction, and push the boundaries of what technology can achieve.
authors:
  - admin
date: '2025-01-23'
lastmod: '2025-01-23'
draft: false
featured: true
image:
  caption: ''
  focal_point: ''
  preview_only: false
projects: []
---

**2025 marks a pivotal year for artificial intelligence.** With advancements accelerating at an unprecedented pace, we stand on the brink of an AI revolution that promises to reshape industries, redefine human-machine interaction, and push the boundaries of what technology can achieve. To truly understand where AI is right now, it's important to look into the past. Especially if we are to make conclusions about the future of AI, its important to look at the trials and tribulations the field has dealt with through history. 

AI researchers have made numerous achievements in the past couple of decades. In 1972, "MYCIN", an expert engine was developed to identify bacteria causing blood infections and to recommend antibiotic treatments. In 1997, IBM's well-known "Deep Blue" beat Gary Kasparov and became the first computer to beat a chess champion in a match under tournament conditions. At the same time, various speech recognition models such as HEARSAY were being developed. What all these artificial intelligence systems have in common, however, is that they are rarely considered intelligent. Deep Blue was critiqued as beating Kasparov merely because it could brute force a solution. "Autocorrect is not considered *intelligent* because it merely scans a dictionary and matches to the closest known word." 

In the case of the diagnostic model MYCIN, the same applies:

MYCIN was described as an Artificial Intelligence (Proc Annu Symp Comput Appl Med Care. 1977 Oct 5:66–69.). As an LISP program, it was designed to be a medical consultant, to tend to the fact that the medical industry is in dire need of computational aid. Doctors often play the role of sole decision-makers and face immense time constraints in their work. As a medical consultant, it was able to diagnose issues in blood samples with a certainty factor to help aid medical professionals. Take a look at an example rule, one of the 600 this program contains:

```
(defrule 52
if (site culture is blood)
(gram organism is neg)
(morphology organism is rod)
(burn patient is serious)
then .4
(identity organism is pseudomonas))
Rule 52:
If
```

```
THE SITE OF THE CULTURE IS BLOOD
```

```
THE GRAM OF THE ORGANISM IS NEG
```

```
THE MORPHOLOGY OF THE ORGANISM IS ROD
```

```
THE BURN OF THE PATIENT IS SERIOUS
Then there is weakly suggestive evidence (0.4) that
```

```
THE IDENTITY OF THE ORGANISM IS PSEUDOMONAS
```

Rule 52 is simple and makes it clear what MYCIN is doing when it identifies an organism such as pseudomonas.

The AI Effect states that when a model's inner workings are understood when it becomes successful in its goals, it no longer is AI. Rather, it is merely a computer program. In the case of MYCIN, knowing the exact rules the computer used to come to its conclusion makes it seem like a computer program and not AI anymore.

## Fast Forward to Gemini

A black box AI is an AI model where the inner workings of its computational processes are unknown. You feed the program some information, and it will give you an output. How it came to that output is out of the reach of even those who made it. Most of today's popular AI falls under this category and it's not without its failings. From an ethical perspective, not knowing how the model reached its conclusion makes it difficult for the public to accept it – especially in cases as important as patient care.

Fast forward to 2024, new and improved diagnostics models such as Med Gemini 2.0 Flash exist. Take a look at its ability to read a CT Abdomen scan and diagnose pancreatitis:

https://x.com/i/status/1867329568404652253

At this point, Gemini is considered an AI. Its ability to read the scan and diagnose is magnificent, but in my opinion, what truly makes it part of the AI category is that it is not truly understood yet. Since it uses machine learning, specifically a neural network, it is impossible to figure out why it works the way it does.

## Complications

The AI Effect changes public opinion to see the previous revolutionary advances of AI as "just software" while continually overhyping and inflating what will come of the current breakthroughs. Public opinion of AI continues to be inflated with overpromises and will only remain focused on what has yet to be solved. With time, AI research will underdeliver and fall out of the public's high reputation. The cycle of hype within AI history is well documented. For the past 60 years, the periods of booms and winters follow like a recipe. The hype cannot be sustained forever, then comes the disappointment, media coverage falls, businesses cut funding, and research dies.

*Jaeden Rotondo*