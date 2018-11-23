---
layout: post
title: Model Based or Model Free?
comments: true
---

In the context of robotic control, a model is a construction to predict how the given system will evolve in the future as a result of actions executed by the agent. *Physics* is just one kind of a model, that expressed the world by a certain set of quantities (such as mass, friction, velocities) to simulate how some of these quantities will evolve in the future. Well established tools of optimization are used to find a sequence of actions to reach a desired goal by exploiting the knowledge of a model. One might not use optimization, one can also try to solve for inverse kinematics. Anyways, I will not delve in details of this and come to this topic later.

In this note, I will assume that you already know what a model means. You can see my talk to know why we should learn models instead of using analytic models if the goal is to build agents capable of performing a general set of tasks. There are two kinds of models that exist: forward and inverse.

If we think about in great detail, knowledge that one should even build a model is a very high-level idea. It is possible that the notion of models emerge when an agent attempts to solve a multitude of tasks. The reason for pursuing this line of work is that, although we can build in that one should have models (especially forward models) the inference methods become complicated and therefore getting actions becomes non-trivial. Maybe if the models evolve as a natural outcome of model-free systems then we will also know how to easily use the models. 

The fact that models are required is also questionable. It is clear by introspection that we do seem to possess some kind of models. We can imagine what will happen if we act in a certain manner. If we are to be believe the idea of model-free leading to model-based, then at sometime by just optimizing for the rewards the agent manages to obtain models. What kind of learning mechanisms might be at play? I think a simple explanation might be emergence of memory cells -- it would have been easy for early organisms to associate if a current action will lead to success in the (near) future. Such memory cells that work by association might be product of mutation in evolution or something.

Time delayed associations -- that is basically the forward model.


{% include disqus.html %}
