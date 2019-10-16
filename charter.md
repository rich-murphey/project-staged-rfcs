# Charter for Project: Staged RFCs

## Summary

The goal of this group is to document and improve our feature design
process, beginning roughly from the point that we decide to embark on
a piece of design and ending with the point where the feature is fully
implemented and stabilized.

The goals are to create a process that ensures:

* easy to follow which things Rust team(s) are working on now
* easy to see the current state of the project
* we not only document the design but some of the reasons and key decisions behind the design
* features in the end product are documented
* features are implemented in a timely fashion
* for projects that wind up blocked, we have documentation of why

## Roadmap

## Motivation

### Problems we aim to solve

**Design process is ill-documented and disjointed.**

Our existing design process is not, as far as I can tell, documented
in any specific place. It consists of a number of stages that range in
formality and which take place over a number of repositories. There is
no "central place" that one can go to to follow a particular bit of
design from start to finish, or to get a good handle on the current
status.

To make this more clear, when I say the "existing design process", I
am referring to the full set of things that happens in the course of
designing and shipping a feature, which includes the following:

* The pre-RFC process
* Opening an RFC
* Adjusting the RFC in response to feedback
* Landing the RFC
* Creating a tracking issue
* Doing implementation
* Adjust design through FCPs and other changes
* Stabilization report
* Writing of documentation

This process has evolved in a somewhat ad-hoc fashion and it shows.

**It is unclear what level of commitment is implied by an RFC.**

RFCs are only the first stage in a multi-step feature development
process. We often make changes -- sometimes quite significant ones --
after the RFC is accepted. However, we *also* tend to spend a lot of
time hammering out fine details in the RFC threads. Sometimes this
leads to surprise, for example when a careful compromise that resulted
from the RFC process winds up being overturned during the
implementation phase. It also leads to frustration, as we often get
blocked in the RFC process, unable to make progress even when there is
a lot of consensus, and only small details remain to be hammered out.

Examples:

* Modules, where we hammered out a design over several RFCs that was
  later revisited and significantly revised. This worked out well in
  the end, but also resulted in some initial surprise ("why are we
  revisiting the syntax now?").
* `Try` trait RFC, where we accepted a design a for the `Try` trait
  which, after having gained significant experience, many feel is no
  longer the right design (especially many of us on the lang
  team). What is the process for a "restart" here?
* RFC 2753, where I think everyone agrees that a new ABI is needed,
  but the discussion is really going back and forth on the meaning of
  **stability**.  Perhaps this could be deferred.

**RFC threads are hard to follow.**

RFC threads in particular are difficult to follow. This is because all
discussion takes place in the context of a single github thread and
covers a wide range of topics, ranging from core motivation to minor
details of the design to the choice of wording.

We would prefer to find ways to make our conversaions more incremental
and targeted, so that the purpose of each individual discussion is
more clear. We should use tracking repositories and summaries to help
keep state "in between" conversations, rather than requiring everyone
to read up on the full background topic.

**Design discussions are cyclic: unable to settle contentious issues.** 

It often happens that we wind up discussing the same points over and
over when having design discussions. This is (in part) a by-product of
things being hard to follow: people are not able to catch up on the
previous state, and so they just jump in without context. To some
extent, people being people, that is inevitable, so it's also
important to have a process that lets us quickly "discard" attempts to
re-open settled topics, but in a friendly way.

**Unbounded queues and "limbo" states.**

The current process often leaves development in a sort of limbo. There
are, for example, a large number of unstable feature gates, and it's
unclear for many of them what (if anything) can be done to bring the
feature into a shippable state. There are other RFCs that land but
never get any implementation -- and of course many RFCs never get
attention at all. In general, we should be better about seeing a
feature through from beginning to end, and we should make it more
clear when things are in a limbo state.

## Design space summary

Things to cover:

* Python PEPs
* C++ standards proposals
* TC39 staging system

## Related work

TBD
