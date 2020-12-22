---
layout: _post
title: "Climbing towards NLU: On Meaning, Form, and Understanding in the Age of Data"
date: 2020-12-22
---

This is a short summary of [Bender and Koller's 'Climbing Towards NLU: On Meaning, Form, and
Understanding in the Age of Data'., 2020](https://www.aclweb.org/anthology/2020.acl-main.463/).

This paper aims to argue that a system exposed only to form in its training has a priori no way to learn meaning. Language modelling
tasks cannot lead to the learning of meaning, as only form is used in the training data. The paper advocates for an alignment
between claims and methodology.

The hype around large LMs and the danger this may pose to the field is evidenced in the misleading language used in academicallyoriented publications, where gross overclaims of model capabilities, such as ‘a model that understands’ and ‘machine
comprehension’, are used. Such statements only serve to feed the AI hype in popular press and the use of imprecise language tends
to occur when we don’t fully comprehend what large LMs implicitly represent about language. The paper argues that instead, a
greater effort should be made to explicitly define terms, in order to accurately represent the capabilities of NLP systems as the field
grows. I agree with this point as oftentimes, it seems that the media and the academic field create an echo chamber, using
sensationalist language to fuel the ‘hype’ around the field. Mainstream media often fails to explain the workings and the research
behind these models, leaving the public forced to trust that these ‘black-box’ methods work.
The terms ‘meaning’ and ‘form’, in the context of the paper, are then explicitly defined. ‘Form’ is taken to mean ‘any observable
realisation of language, marks on a page, pixels or bytes, movement of the articulators’. ‘Meaning’ is described as ‘the relation
between form and something external to language’. Formally, meaning is represented by a pair (e, i) of natural language expressions
e and the communicative intent i they can evoke. From this, ‘understand’ can be defined as ‘the process of retrieving i from a given
e’. ‘Standing meaning’ s, or the ‘meaning that remains constant across all of its possible contexts of use’, allows us to formally
assume that when the listener hears an expression e, they can then reconstructs s and use their own knowledge of the
communicative situation and the speaker’s state of mind and intention to deduce i. This definition differs from the one we saw on
distributional semantics, which was described as ‘understanding a term by the distribution of words that appear near the term’. This
definition doesn’t seem to align with the thesis of this paper as it is the form of the text, and not ‘something external to language’
that is used to claim the model ‘understands’. From these definitions, the argument of the paper is expanded to state that if the
training data is only form, there isn’t sufficient signal to learn the relation m (meaning) between said form and the non-linguistic
intent of the human language users, nor any relation between e (expression) and s (standing meaning), assigned by the linguistic
system to each form.

The paper presents several thought experiments to demonstrate its point, denoting ‘intelligence’ as ‘meaning and understanding’.
From Searle’s Chinese Room, it concludes that independent of whether passing the Turing test would mean a system is intelligent, a
system trained only on form would fail a sufficiently sensitive test, because it would lack the ability to connect its utterances to the
world. The Octopus Test and the example of asking GPT-2 ‘Help!... What should I do?’ reinforce the point that language models fail
when we test their understanding of ‘meaning’ by asking them to solve tasks that require reasoning and creative thinking.
From observing human children, the paper argues that passive exposure isn’t sufficient to acquire a linguistic system; joint attention,
an awareness of what another person is attending to, and an idea of what they’re intending to communicate are all required.
However, it recognises that grounding distributional representations in the real world is challenging and proposes tackling these
issues by training distributional models on corpora augmented with perceptual data or looking to interaction data.

The paper brings into question whether the field is tackling the correct problems. It pushes for a ‘top-down’ approach, where focus
is kept on the overarching, end goal of finding a unified theory for the whole field. Whilst a ‘bottom-up’ perspective may currently
be responsible for the hype, excitement, and general optimism in the field, it fails to address the question of whether the ‘right hill is
being climbed’. Given that we will only be able to tell in hindsight, the paper proposes five ways of mitigating error: cultivating
humility and asking top down questions, being aware of the limitations of tasks, valuing and supporting the work of carefully
creating new tasks, evaluating models of meaning across tasks, and performing thorough analysis of both error and successes. It
addresses prevalent counterarguments against the main thesis succinctly and effectively, before concluding that, in contrast to the
current hype, meaning cannot be learnt from form alone. Large LMs do not learn meaning. It finishes by offering thoughts on how to
maintain healthy optimism in the field. Calls are made to spur a top-down perspective in the field, to increase the use of precise
language, especially when talking about the successes of current models, and to encourage humility in dealing with natural
language. I inherently agree with the thesis and the conclusions of this paper – the methods to mitigate error could be generalised
to other fields where a lot of hype has recently been generated too. The use of examples via thought experiments and the answers
to the counterarguments make for a solid argument, advocating for chartering a more attentive and vigilant course in the field. 
