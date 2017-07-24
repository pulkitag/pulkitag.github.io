---
layout: post
title: One shot Visual Imitation Learning
comments: true
---

Wouldn't it be great if robots can learn to perform complex tasks by watching videos
of humans perform the same task? This has been a dream in robotics and this topic
that has attracted a lot of investigation from the early days (cite the Japanese papers).
What is so hard about this problem?

Let us consider a very simple problem where a human picks an object and keeps it
at another location. When a robot observes this video, it has to infer the intent (goal)
of the human action. For instance, given only the observation of one video it is not
possible to attribute what is more important -- the
specific movement of the hand, the specific position where it grabbed the object or the fact that
the object was grabbed and then placed at a certain point. A human observing the video would trivially
attribute that the most important part of the demonstration was that the object was
displaced to a different location. This thought experiment suggests that humans have a prior
over what is important/interesting and what is not.

One approach to learning from a video of the demonstration is to extract the pose of human hand,
use an appropriate function to transform it into robot's hand pose (note that such a mapping
is not guaranteed to exist due to potential anatomical differenced in human and robotic hands)
and execute the same set of actions that the human performed.
Even if we were to assume that it is possible to perfectly
extract the human hand pose and map it to the robot's hand pose, this technique would work only
in the simplest of environments where the environment observed by the human and the robot
are exactly the same and robot sees the environment from the same camera viewpoint from
which the human performed the demonstration.

A more nuanced approach would be to identify what objects in the environment were manipulated
by the human and then manipulate the same objects.
