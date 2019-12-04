---
layout: post
title: Jacob Beel
post-title: Misadventures in Making Magic
excerpt: I turned generating D&D spells into a class project. It didn't work out.
---

I ended up turning the experiments I was doing on my own with D&D spells into a class project. Things were promising, and we had grand ideas about what we wanted to accomplish. In order to receive guidance on how we should tackle the issue, we spoke with Dr. Riedl, a professor who works at the interaction of HCI and Machine Learning at Georgia Tech. He pointed us in the direction of "start simple." This makes sense, of course. Why waste effort doing something complicated when something simple will get you 90% of the way there? Of course, there's nothing at all wrong with this advice, it was the _right_ thing to do, but there were problems that we did not overcome.

The main problem to overcome during this project was __data__. There are two main things that are wrong with the data in this problem:

- The SRD only has about 430 spells available. Not nearly enough to constitute any amount of training data.
- When we encoded spell statistics, we ended up with a 16 item vector. This is a very small amount of data to map to some very long spell descriptions.

These two things led to not-so-fun results. We tried to circumvent the training data problem by using rule-based permutation to generate more training data. This worked well enough and, worst case scenario, it would just be like training on the original 430 and overfit like crazy. Unfortunate, but not catastrophic. The catastrophic part comes in when we try to map 16 features to very long spell descriptions. We did this by up-sampling so that we'd have high enough dimensionality. Turns out, this didn't actually matter. Since the spell statistics varied so little and the spell descriptions varied so much, we ended up generating "sentences" that were essentially repeated versions of some of the most common words repeated ad-nauseum. For example:

`spell spell spell spell spell spell spell...`

You get the idea.

So, where do we go from here? Lots of things. There's an entire section in our report on what we think could possibly make this task viable and I hope to explore them one day:

- Increase the feature space: If the problem is lack of features, let's increase the feature space! How? That's... not as clear right now. There are a lot of ways this could be done and there's a lot swarming in my head but maybe I'll write a blog post about what these ideas are down the line.

- Flip the problem: From descriptions, generate stats? Could lead to some interesting test-cases. For example, throwing magic from other pieces of fantasy (Harry Potter, LotR, etc.) into this black box and converting them in to D&D spells. Could make for some fun stuff

- Or, rework the apprach entirely: Move on to something more complex? Maybe it's time.

Hopefully next semester will give me a bit more time to do this stuff! Now, it's time to study for finals.