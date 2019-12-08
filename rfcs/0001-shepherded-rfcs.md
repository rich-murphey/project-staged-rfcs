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
  
Core ideas of the proposal:

* Proposals begin as issues on the lang-team repository with corresponding internals threads(s)
* When selected, proposals become shepherded items, and they are
  assigned shepherds and a lang team liason
* Each proposal gets a dedicated repository which can be used to
  collect design notes and the like and which stays active until the
  proposal is stabilized
  
**Note:** If this RFC is adopted, then existing T-lang RFCs will be
asked to migrate to the lang-team issues and (eventually) closed as
postponed.

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
    * Since the internals forum is preferred for ongoing discussion, 
      to avoid confusion the github issues will be closed for comments.
      The template will include a link to a thread on
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

## Proposal template

The proposal template will be fairly minimal. It will include the following information:

* key people involved in the proposal
* a short summary of the problem
* link(s) to internals discussion thread(s) where the proposal is being discussed in more depth
* text indicating the role of this issue (in particular, that 
  discussion is directed to the internal forum, not github.)
  
## Proposal issues

The proposal issues are meant to serve more as a "table of contents"
that lets people catch up on the high-level idea (and current
thinking) for a given proposal. The only comments that are expected
will be information about scheduling (e.g., a meeting has been
scheduled) or other such events.

If we find that issues are being used for discussion, we may need to
create a bot that either locks the issue automatically or else which
responds (and hides) people's attempts to post comments that don't fit
particular templates.

## Reviewing proposals

The lang team shall establish a proecss for regularly reviewing
pending proposals. The expectation is that this will take the form of
a dedicated meeting where each member comes prepared with a small
number of proposals for which they would like to serve as the liason
(or shepherd). There will also be some mechanism for proposals to be
**nominated** when it seems like they need additional feedback from
the team. The meetings will be announced on the [Inside Rust blog] and
on [the lang-team calendar].

[Inside Rust blog]: https://blog.rust-lang.org/inside-rust/
[the lang-team calendar]: https://github.com/rust-lang/lang-team/#meeting-calendar

## Shepherds

When a project is selected, it is assigned one or more **shepherds**
(discussed here) and a **lang-team liason** (discussed in next
section).

**Shepherds** are basically the primary people who are trying to move
the proposal along. They may be on the lang team, but they don't have
to be. In fact, being a shepherd is a great way to get started on the
lang team.

### Being a shepherd is a commitment

* Shepherds are supposed to keep the lang team abreast of
  the current status of the design and discussion. This can be done by
  attending meetings, but it could also be done by blog posts or
  written reports.
* When a design concern or conflict arises, shepherds should help to
  see it resolved. This means a few things. First and foremost, they
  have to work to **understand and document the considerations at
  play**, and be prepared to summarize those.
    * (Note: they don't necessarily have to do all this work
      themselves! I would like to see us making more use of
      [collaborative summary documents], which allow us to share the
      work of documenting concerns.)
* Shepherds should also work to help resolve the conflict, possibly by
  scheduling one-off meetings or through other means.
* Finally, shepherds often become experts in their area. As such, to
  the extent that they can, we would like them to help to answer
  questions that arise about similar topics in the future (even if
  they are not actively shepherding that area anymore).

### Accepting a project if a commitment from the lang team

From the [Shepherds 3.0 blog post][3.0]:

[3.0]: http://smallcultfollowing.com/babysteps/blog/2019/09/11/aic-shepherds-3-0/

> I want to emphasize this part of things. I think the lang team suffers
> from the problem of doing too many things at once. Part of agreeing
> that someone should shepherd topic X, I think, is agreeing that we
> should be making progress on topic X.
> 
> This implies that the team agrees to follow along with the status
> updates and give moderate amounts of feedback when requested. 
> 
> Of course, as the design progresses, it is natural that lang team
> members will have concerns about various aspects. Just as today, we
> operate on a consensus basis, so resolving those concerns is needed to
> make progress. When an item has an active shepherd, though, that means
> it is a priority, and this implies then that lang team members with
> blocking concerns should make time to work with the shepherd and get
> them resolved. (And, is always the case, this may mean accepting an
> outcome that you don't personally agree with, if the rest of the team
> is leaning the other way.)

## Lang team liason

The **lang-team liason** is someone from the lang team who is also
following along with the project. They may or may not be following
that closely, but it's their job to represent the project in lang team
meetings (at least, if the shepherds can't attend) and to help ensure
that the project keeps moving. 

The lang team will ensure that liasons are not overburdened. In
particular, we will try to limit the number of things that a liason
can do at one time, so as to ensure that they have bandwidth
available.

## Repository

When we create a repository for a proposal, that repository will be
created in the `rust-lang` github org. It will be given a name like
`project-xyz`, where `xyz` is related to the name of the feature (for
example, [`project-ffi-unwind`]. The shepherds as well as the
lang-team will be given write access to the repository.

[`project-ffi-unwind`]: https://github.com/rust-lang/project-ffi-unwind/

The precise template for these repositories is not specified in the
RFC but is something we expect to evolve over time. However, it will
include at least the following:

* a 'charter', describing the goals of the working group;
* RFC text, written collaboratively;
* summaries of key decisions, indicating the pros and cons and possible options
    * think of the write-ups that were done as part of deciding the async-await syntax

## Transitioning to the new system 

In order to transition to the new system, the existing T-Lang RFCs on
the rfcs repo will need to be migrated to lang-team issues. To aid in
this process, we will send a message to each RFC, giving instructions
and guidance on how to do that. After a certain amount of time, we
will close the RFCs as "postponed".

# Drawbacks
[drawbacks]: #drawbacks

The RFC repo no longer serves as a place to go to see all the pending
proposals -- instead, the internals discussion board plays that role.

# Rationale and alternatives
[rationale-and-alternatives]: #rationale-and-alternatives

There are any number of variations possible. This section includes a
few of the key notes.

**Where should the project repos be created?** The repositories for
each project are created in the rust-lang org. We considered creating
them in people's personal Github accounts, but using the rust-lang org
ensures that the full history will always be available, and will also
aid in moderation.

**Where should discussion take place for proposals?** The current RFC
specifies that discussion takes place on internals threads. There are
any number of other possibilities:

* People could discuss in the issues themselves -- but we've seen the
  problems that arise with long issue threads, which quickly get out
  of date, particularly as projects evolve.
* People could create their own repositories already in the proposal
  state, but that would potentially create a lot of repositories. This
  would also make moderation more difficult, particularly if those
  repositories are not in the rust-lang org.

**RFC migration.** We could automatically move all RFCs to
issues. However, it seems better to let users opt to move
themselves. It requires less tooling and it also offers folks a chance
to just close older RFCs where the authors have moved on.

# Prior art
[prior-art]: #prior-art

## TC39

XXX

# Unresolved questions
[unresolved-questions]: #unresolved-questions

This RFC does't have a "stabilization period" like other
RFCs. However, the RFC does leave a number of details loosely
specified, with the expectation that they will be adapted over time:

* The precise way that the lang team will conduct regular reviews of pending proposals
* The precise template for RFC repositories
* The precise duties of a shepherd or liason

# Future possibilities
[future-possibilities]: #future-possibilities

None.
