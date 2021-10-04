# KIP-0: KeeperDAO Governance
```
kip: 0
title: KeeperDAO Governance
author: hazard <hazard@keeperdao.com>
status: draft
tags: none
created: 2021-09-02
replaced-by: none
replaces: none
```
## Preface


### Summary
KIP-0 defines a simple format for writing KeeperDAO improvement proposals (KIPs), and illustrates how a KIP goes from idea to reality, through consensus. Finally, it defines governance helpers called Sophons that coordinate the governance process.

### Background
Proposals, and the process they go through in order to reach consensus, are two of the most basic elements of DAO governance. As a DAO, one of our primary missions is to enable as many people as possible to join, contribute, and add value, and that begins with setting up a basic set of expectations for how governance operates.

### Proposal
Adopt the specified guidelines below, defining the KeeperDAO governance.

### Templates
   - [KIP-0-T1 Sophon onboarding](./KIP-0-T1.md)
   - [KIP-0-T2 Sophon offboarding](./KIP-0-T2.md)


## KeeperDAO improvement proposals

### What is a KIP?
A KIP is a proposal that an author or group of authors would like to be evaluated by the members of KeeperDAO. The members of KeeperDAO shall work with the author of a KIP to review and refine its content, before using an agreed-upon consensus procedure to collectively determine whether to adopt or decline the final proposal. 

### Minimum style requirements
A KIP should be written in plain language, formatted as [Markdown](https://en.wikipedia.org/wiki/Markdown). It should clearly and completely describe the proposal, its motivations, and why the author believes it improves the status quo. Where applicable, it should also describe a set of steps to enact the proposal. Authors and editors should work together to ensure that the KIP meets at least the following minimum style requirements:

- **Consistency**: Does it contradict itself or any other non-historical KIP?
- **Accuracy**: Are its data, arguments, and understanding of systems complete, accurate, and up-to-date?
- **Feasibility**: Does it propose or require things that are impossible ot impractical to accomplish?
- **Verifiability**: Can anyone verify for themselves that an implemention did occur in the way described by the KIP?


### Recordkeeping
KIPs form an archival series, meaning that each KIP has a unique archival serial number, and is not able to have its essential content changed once it has become finalized. At the top of every KIP is a header which contains metadata that editors can use to help organize the governance record. 

- `kip` The proposal number, for example, `0`.
- `use` *(Optional)* The name of the proposal template being used.
- `author` A list of author names (or usernames if anonymous), along with e-mail addresses or another way to contact them.
- `status` Proposals have a status, one of the following set: `draft`, `review`, `last-call`, `final`
- `tags` Comma-separated list of tags from the set `accepted`, `rejected`, `implemented`, `withdrawn`, `historical`.
- `created` Date that the proposal was created. Should be in [ISO 8601](https://wikipedia.org/en/wiki/ISO_8601) format (YYYY-MM-DD).
- `replaced-by` *(Optional)* KIP that replaces the KIP.
- `replaces` *(Optional)* Comma-separated list of KIPs that the KIP replaces.

These fields and their values may be changed in the governance repository without the need for a new consensus, as long as the change is recorded in the repository and carried out by those delegated to do so.

## Governance lifecycle

1. Author posts KIP draft on forum 
    1. When a new KIP appears on the forum, a notification and summary shall be posted to a relevant channel.

2. Crowd Consensus
    1. The author shall allow sufficient time for, and make a best effort to reach, rough consensus with the community about the content of the draft proposal. 
    2. When the author determines that rough consensus has been reached, the author shall communicate their intention to submit the proposal to the governance record for review.
    3. The author shall make a best effort to allow sufficient time for all interested parties to post final comments on the draft before formal submission.
    
3. Merge to Git repository
    1. The author shall open a pull request to the governance repository, aided by a Sophon if necessary.
    2. A Sophon shall add the header fields to the KIP, and mark its status as `draft`, before merging it.

4. Sophon Consensus
    1. Sophons shall maintain a public queue of the merged KIPs to be reviewed. This queue shall be ordered chronologically according to the date of the git merge.
    2. Sophons must make a best effort to review each KIP in order, and acheive rough consensus.
    3. When a KIP enters review, a Sophon shall change the KIP status from `draft` to `review`.
       1. During review, Sophons shall make a best effort to conduct their deliberations in public and record minutes, as well as be available for public feedback.
       2. If Sophons cannot reach rough consensus, the proposal will return to `draft` status.
       3. Otherwise, the Sophons will assign the KIP a voting period and change its status from `review` to `last-call`.

5. Last call period
    1. Sophons and the KIP author shall make efforts to notify interested parties, allow sufficient time to facilitate discussion, and uncover any remaining objection or correction to the proposal before objection voting begins.

5. Objection Voting
    1. Objection voting shall run for a minimum of 7 days, except for matters which present a clear, imminent danger to users, protocols, or the DAO.
    2. The vote shall have two options, 'Present' and 'Object', and shall include a prominent message explaining the difference between apparent consensus and majority voting.
    3. Best effort shall be made to notify interested parties about the objection vote once it is live.
    
6. Ratification
   1. If enough tokens select the 'Object' option at the close of the vote, the KIP does not have tokenholder consensus, and it returns to `draft` status. If there is a non-zero quorum requirement, and not enough tokens have selected the 'No objection' option, then the proposal is returned to `draft` status. Otherwise, the proposal is assigned `final` status.
   2. The result of the vote shall be communicated via Discord and Twitter.

## Sophons 

Sophons are individuals empowered by the DAO to review, analyze, and publish non-binding recommendations on KIPs. They should "speak for the protocol," rather than their own interests, and be knowledgeable about the subjects being considered. 

Their role is to ensure that every KIP has been given adequate attention before it is put in front of tokenholders for a vote, and that tokenholders are provided with the opinion of qualified stakeholders in case they cannot judge for themselves.

### Sophon onboarding process 

This section defines a process for onboarding one or more Sophons. 

Use the template located at [KIP-0-T1.md](./KIP-0-T1.md).

### Sophon offboarding process 

This section defines a process for offboarding one or more Sophons.

Use the template located at [KIP-0-T2.md](./KIP-0-T2.md)
