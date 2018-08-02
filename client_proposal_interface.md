# Client proposal interface

## Summary

Project talent members need to be able to edit a proposal document together with very lightweight flow for creating a breakdown and adding time and costs to it.

## Motivation

Experts that currently sell time to clients collaboratively tend to struggle with the work involved in bringing together everything that is needed for a proposal and then presenting it in a simple manner for clients.

I believe that if it was easy to collaboratively  create a document listing the work with time and costs attached it would allow talent to pitch for work with clear communication between all involved.

## Outcome

Needs designs

* Ability to add a title and description to the proposal
* Ability to add a nested list breaking down key deliverables
* Ability to add time in days or hours to a list item
* Total time and cost shown as added
* costs will be calculated either using custom input or rate multiplied by time
* rate can come from fixed time unit rate on the project
* rate can come from adding user and adding client rate and talent rate to them

## Implementation

### Interface

* Library - [Draft.js](https://draftjs.org/)

1. Title will be it's own for field
2. Document body should be rich text editor that allows:
	1. 3 different types of header
	2. hyperlinking
	3. bold
	4. nested lists (check, ordered, unordered)
3. Each line of nested list needs to allow addition of time and cost
4. Can add a project rate to top column that also has total time and cost
5. @ symbol will allow user to add member to agreement.
	1. If member hasn't been added to agreement yet then pop-up allows user to set rate
6. Each member needs to have time and rate

### Actions & Reducers

1. fetchProposals action
2. Proposal reducer
	1. CREATE_PROPOSAL
	2. FETCH_PROPOSAL

### Queries

1. `projects/project_id/proposals`

### Backend
