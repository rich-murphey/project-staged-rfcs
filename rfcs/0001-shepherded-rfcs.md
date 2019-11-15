- Feature Name: (fill me in with a unique ident, `my_awesome_feature`)
- Start Date: (fill me in with today's date, YYYY-MM-DD)
- RFC PR: [rust-lang/rfcs#0000](https://github.com/rust-lang/rfcs/pull/0000)
- Rust Issue: [rust-lang/rust#0000](https://github.com/rust-lang/rust/issues/0000)

# Summary
[summary]: #summary

This RFC proposes a new scheme for managing RFC development entitled
"shepherding". It is initially intended for use by the lang team, but
is written in a way that it could be adopted by other teams as well.

Core principles:

* **Transparent:** The priorities and active work items of the team
  should be well-documented
* **Focused:** There will be relatively few open PRs on the RFC
  repository at any given time, but each of them will represent a
  topic that the lang team is actively interested in advancing
* **Room for serendipity:** One of the goals is to make a clearer
  advancement path for "bottom up" proposals that were not on the
  original roadmap -- right now such proposals can often languish in
  "RFC limbo" for far too long.
* **Follow-through:** Another goal is that once we begin work on
  something, we take it to its logical conclusion (e.g.,
  stabilization) before picking up other things (or we explicitly
  decide to stop).
* **Path to membership:** A final goal is to create a path by which
  people can gain more experience with how the lang team operates and
  perhaps ultimately be asked to join the team.

# Motivation
[motivation]: #motivation

In this motivation, we speak specifically of the lang-team. However,
many of the problems described here are more general.

# Guide-level explanation
[guide-level-explanation]: #guide-level-explanation

*The following is sample text that would be published to describe how
to propose a new language feature.*

If you would to propose a new language feature, there are a few steps
to the process:

* **Step 1: Proposal** -- in this stage, you propose an area for
  exploration. Proposals are made by opening an issue on the lang-team
  repository with a fixed template.
    * These issues are not a place for discussion and will be closed
      for comments. The template will include a link to a thread on
      internals for discussion purposes.
    * The lang team periodically reviews all open proposals, looking
      for ideas that seem like a good candidate to go forward.
    * In some cases, the team may opt to schedule a meeting to discuss
      a proposal in more depth. In such cases, you would be encouraged
      to attend.
* **Step 2: Preliminary design** -- if the lang team decides to pursue
  an idea, it will be assigned one or more **shepherds** (the folks
  doing most of the work, not necessarily on the lang team -- possibly
  you!) and a **lang team liason**.
    * We'll also create a repository to begin work on the actual RFC
      and design.
    * For more complex designs, this repository will serve as the
      central home for this feature, collecting not only the RFC text
      but also design notes, meetings minutes, and whatever seems
      relevant.
    * Depending on the complexity of the proposal, we may also create
      a "project group" (see RFC XXX).
* **Step 3: Implementation** -- once the design seems sufficiently
  baked, we can begin work on implementation. It is important to note
  that the design may continue to involve based on feedback from
  implementation.
    * In order to enter this stage, it will be necessary to line up
      some folks to work on the implementation (these can be the same
      as the shepherds) and -- importantly -- a **compiler team
      reviewer** (who will be reviewing the related PRs?).
* **Step 4: Stabilization** -- once every is ready, we will create a
  **stabilization report** documenting the final details and **move to
  stabilize**. At this point, the feature will be usable from stable
  Rust.

# Reference-level explanation
[reference-level-explanation]: #reference-level-explanation



# Drawbacks
[drawbacks]: #drawbacks

This 

# Rationale and alternatives
[rationale-and-alternatives]: #rationale-and-alternatives

- Why is this design the best in the space of possible designs?
- What other designs have been considered and what is the rationale for not choosing them?
- What is the impact of not doing this?

# Prior art
[prior-art]: #prior-art

Discuss prior art, both the good and the bad, in relation to this proposal.
A few examples of what this can include are:

- For language, library, cargo, tools, and compiler proposals: Does this feature exist in other programming languages and what experience have their community had?
- For community proposals: Is this done by some other community and what were their experiences with it?
- For other teams: What lessons can we learn from what other communities have done here?
- Papers: Are there any published papers or great posts that discuss this? If you have some relevant papers to refer to, this can serve as a more detailed theoretical background.

This section is intended to encourage you as an author to think about the lessons from other languages, provide readers of your RFC with a fuller picture.
If there is no prior art, that is fine - your ideas are interesting to us whether they are brand new or if it is an adaptation from other languages.

Note that while precedent set by other languages is some motivation, it does not on its own motivate an RFC.
Please also take into consideration that rust sometimes intentionally diverges from common language features.

# Unresolved questions
[unresolved-questions]: #unresolved-questions

- What parts of the design do you expect to resolve through the RFC process before this gets merged?
- What parts of the design do you expect to resolve through the implementation of this feature before stabilization?
- What related issues do you consider out of scope for this RFC that could be addressed in the future independently of the solution that comes out of this RFC?

# Future possibilities
[future-possibilities]: #future-possibilities

Think about what the natural extension and evolution of your proposal would
be and how it would affect the language and project as a whole in a holistic
way. Try to use this section as a tool to more fully consider all possible
interactions with the project and language in your proposal.
Also consider how the this all fits into the roadmap for the project
and of the relevant sub-team.

This is also a good place to "dump ideas", if they are out of scope for the
RFC you are writing but otherwise related.

If you have tried and cannot think of any future possibilities,
you may simply state that you cannot think of anything.

Note that having something written down in the future-possibilities section
is not a reason to accept the current or a future RFC; such notes should be
in the section on motivation or rationale in this or subsequent RFCs.
The section merely provides additional information.
