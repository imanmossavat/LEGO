# Reasoning and Abstraction in Large Language Models Trained on a Controlled LEGO Environment

## Introduction

Understanding how large language models (LLMs) reason and abstract is crucial to improving their capabilities and guiding their development toward more intelligent systems. While LLMs have shown impressive performance across a wide range of natural language tasks, their ability to integrate logical reasoning and abstraction remains an open challenge. To study these abilities systematically, it is essential to design controlled environments where LLMs' reasoning processes can be observed and measured in isolation from the complexities of real-world data [2]. One promising approach is to create a simplified, structured world using LEGO blocks, a domain that naturally embodies key concepts such as compositionality and spatial reasoning.


## The Core Idea: A Controlled World

We create a **controlled LEGO world** where everything is governed by simple, interpretable rules. In this world, we can:

- Build LEGO models programmatically using a custom DSL (similar to Bricklayer).
- Represent these models as graphs or sequences for machine learning tasks.
- Design reasoning challenges, such as completing patterns, predicting next steps, or abstracting components.

This controlled setting lets us isolate specific abilities of LLMs—like following instructions, reasoning over sequences, or composing smaller elements into a whole—without the noise of real-world complexities.

## Why LEGO?

LEGO is inherently **compositional**: small bricks combine to create larger structures, and those structures can be broken back into their components. This mirrors how reasoning and abstraction work. By using LEGO, we can design tasks that challenge LLMs to:

1. **Reason Spatially**: Understand how objects fit together or predict what’s missing in a structure.
2. **Abstract**: Learn high-level concepts like "a house" or "a tower" from low-level pieces like individual bricks.
3. **Follow Logic**: Apply rules to transform, complete, or evaluate structures.
4. **Physical**: we can apply physics to bodies made from LEGO, where is the center of graivty, are they stable for example? Can we build a structure whithin certain weigth or dimension constraints.
5. **Tool usage** Another possibility is LLM tool-usage (this is often referred to agentic behavior, but I would avoid using the term agents for funciton calling.) where tools are engines that can work with lego bricks (checking rules, physics, etc...).


Moreover, LEGO models can be represented in ways LLMs can understand, like graphs, sequences, or a custom domain-specific language (DSL). 


## Why Functional Programming?

Functional programming, as used in tools like Bricklayer [1], is ideal for defining LEGO constructs. It focuses on modular, composable functions that describe patterns and structures clearly. This simplicity aligns with the reasoning tasks we want to explore, like recursion for repeating patterns or transformations for logical reasoning. It is porbably handy to create a large dataset by automatic code generation to train the neural network.
We have the option to expose the LLM to the functional program, such as a system that takes the code as input and creates code as output. But in that case, the LLM is not exposed to the LEGO. Interesting question would be multi-modality, where the code is supplied with images.  

## Example Tasks

Here’s how we might train and evaluate LLMs in this environment:

1. **Missing-LEGO-piece prediction**

   - **Input**: A structure with missing pieces in the outer part
   - **Output**: Propose bricks and how they should be placed

2. **Next-LEGO-piece prediction**

   - **Input**: A structure with pieces up to step N
   - **Output**: Propose next brick, and where and how it should be placed

2. **Pattern Recognition**

   - **Input**: A series of LEGO structures that follow a pattern, like alternating colors or symmetry.
   - **Output**: Predict the next brick or complete the missing part.
   - **Goal**: See if the model can learn and extend patterns.

3. **Abstraction**

   - **Input**: A complex LEGO structure.
   - **Output**: Break it into logical subcomponents (e.g., walls, roof, base).
   - **Goal**: Evaluate how well the model identifies higher-level abstractions.

4. **Transformations**

   - **Input**: A model and a rule like "Replace all blue bricks with red ones."
   - **Output**: A new model that satisfies the rule.
   - **Goal**: Study how the model applies logic systematically.

## Future Steps:
In more advanced steps, we would like to explore how this LEGO-based environment can relate to concepts in machine learning, such as symmetries and equivariaces. LEGO structures often exhibit spatial symmetries, and equivariant networks can be employed to provide better inductive biases in the architecture design. We also consider how reinforcement learning (RL) can be applied to further enhance the model's ability to learn through interaction with the environment, enabling it to optimize its reasoning and decision-making processes by interacting with a LEGO environment.



## References

[1] Bricklayer: An Authentic Introduction to the Functional Programming Language SML [1412.4881](https://arxiv.org/pdf/1412.4881)

[2] [ICML Tutorial Physics of Language Models](https://physics.allen-zhu.com/home) 

