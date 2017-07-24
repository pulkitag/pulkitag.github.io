---
layout: post
title: Exploration/Curiosity
---

A short summary of mostly recent and some old papers on exploration and curiosity.

## [Teacher Student Curriculum Learning](https://arxiv.org/pdf/1707.00183.pdf)

The student is required to learn to perform a finite set of discrete tasks. The teacher proposes a task and measures the learning progress of the student. The tasks are sampled proportional to the learning progress (thompson sampling; other sampling schemes also explored). Results are shown for adding numbers and minecraft navigation.

## [Noisy Networks for Exploration](https://arxiv.org/pdf/1706.10295.pdf)

The weights are sampled from a gaussian distribution and the mean and variance are optimized using policy gradients. The idea is by changing the weights, the policy can be modified substantially and therefore lead to more rapid exploration that $$\epsilon$$ greedy exploration. The term noisy networks means that weights are sampled, i.e. noise is injected in the weights.

## [Lifelong Learning in Costly Feature Spaces](https://arxiv.org/pdf/1706.10271.pdf)

Feature evaluation is sometimes costly - for eg, in medical analysis each feature might be a medical procedure. If there are $$S$$ samples, for $$m$$ adversarially chosen related tasks with the same $$N$$ features then $$\mathcal{O}(SmN)$$ feature evaluations are required to learn each task from scratch individually. The paper presents a method for learning tasks from $$\mathcal{O}(S(m+N))$$ evaluations for decision trees and monomials/polynomials.

## [Hindsight Experience Replay](https://arxiv.org/pdf/1707.01495.pdf)

Tasks with sparse rewards are hard to solve. This is because if the reward is sparse, the agent will never succeed and the  gradients will be zero. The main idea of this work is to parameterize the policy and the value function with the current state ($$s_t$$) augmented with the goal ($$s_g$$), i.e. $$(s_t \| s_g)$$ and use the states visited in the past (i.e. hindsight) as targets to train a policy to go to an arbitrary state ($$s_g$$). This is similar to [Learning to Poke](https://arxiv.org/abs/1606.07419), [Universal Value Function Approximators](http://proceedings.mlr.press/v37/schaul15.pdf) and [Rope Manipulation](https://ropemanipulation.github.io/) papers.

Authors use DDPG and in the replay buffer replace the goal with states encountered in the current episode. Because, the encountered states are used as goals, the rewards for atleast some of the transitions is non-zero which helps in learning. Although, the agent is not able to reach the set goal, it still learns how to reach different states. As the agent learns to reach some states, when it is a given a goal state it will get closer to the goal and encounter a new set of visited states which will then be included as goals. After this process is repeated many times the agent will start achieving the goal state. This a very similar idea to the rope manipulation paper, where first an inverse model is learnt and then the exploration is biased towards some human specified states.

Note that all the results are from a low-dimensional state space and not pixels. The idea is neat, but should probably cite other relevant papers :)
