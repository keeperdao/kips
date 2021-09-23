# KIP-0: KeeperDAO Governance 
```
kip: 0
author: hazard <hazard@keeperdao.com>
status: draft
created: 2021-09-02
```
## Preface 

### Proposal
Adopt the specified guidelines below, defining the KeeperDAO governance.

### Summary
KIP-0 defines a simple format for writing KeeperDAO improvement proposals (KIPs), and illustrates how a KIP goes from idea to reality, through consensus. Finally, it defines governance helpers called Sophons that coordinate the governance process.

### Background
Standard and easy-to-follow guidelines let more people participate in governance. As a DAO, one of our primary missions is to enable as many people as possible to join, contribute, and add value. Standards also enable us to build tools and automated systems that enhance the quality-of-life for proposal authors and editors. Doing this properly requires striking the right balance between accessibility, robustness, and formality. 

This KIP takes inspiration from a number of sources, including the Ethereum Improvement Proposal process, the IETF RFC standard, the W3C, and the Maker Improvement Proposal.

### Templates
   - [KIP-0-T1 Sophon onboarding](./KIP-0-T1.md)
   - [KIP-0-T2 Sophon offboarding](./KIP-0-T2.md)

## KeeperDAO improvement proposals 

### Style 

Write your KIP in [Markdown](https://en.wikipedia.org/wiki/Markdown), following the [KIP template](./KIP.template.md). Try to write in plain English, because not everyone is a native speaker. Clearly and completely describe the proposal, and why it is an improvement. 

It doesn't have to be perfect. Publish early and often, and we can make it better together. Governance is about communicating. As long as we can communicate, it will be okay. 

### Header fields

The header is a section at the top of a KIP which contains metadata information about the KIP that computers can use to help organize governance. If you don't know what to write in a field, just write 'none'.

- **`kip`** The proposal number, for example, `0`.

- **`use`** *(Optional)* The name of the proposal template being used.

- **`author`** A list of author names (or usernames if anonymous), along with e-mail addresses or another way to contact them.

- **`status`** Proposals have a status to let people know if what they are reading is a final thing, or just a draft.
   - `draft` For when the proposal has been merged into the governance repository.
   - `adopted` Review has recommended `accept`, and tokenholders did not object.
   - `declined` Review has recommended `reject`, and tokenholders did not object.
   - `withdrawn` Has been withdrawn by the author.

- **`created`** Date that the proposal was created. Should be in [ISO 8601](https://wikipedia.org/en/wiki/ISO_8601) format (YYYY-MM-DD).

### Templates

A KIP can define templates for future KIPs to use when carrying out routine governance processes described in the KIP. These templates ensure that the information being provided each time the process is carried out is consistent, and helps streamline the process in general.

## Proposal lifecycle

### Writing a KIP

1. Discuss your idea with people on the Discord or forum.
2. Write your KIP and post it in a forum thread.
3. Get feedback and try to establish a rough consensus.
4. Open a pull request to this repository, and get an editor to merge it.

### Reviewing a KIP

Once merged, Sophons will research and discuss your proposal to arrive at a non-binding recommendation within 1 month of the pull request being merged. They will recommend one of 2 things:
- `adopt`: the Sophons think the KIP is good and should be adopted by the DAO.
- `decline`: the Sophons think the KIP isn't good and should not be adopted by the DAO. 

### Voting on a KIP

A Sophon must create a Snapshot vote immediately after publishing a recommendation. The vote stays open for 1 week. During this time, tokenholders may use their tokens to vote against the recommendation. 

If enough tokens vote against the recommendation, the KIP remains a `draft`. Otherwise, the KIP status becomes:
- `adopted` if the recommendation was `adopt`.
- `declined` if the recommendation was `decline`.

## Sophons 

Sophons are individuals empowered by the DAO to review, analyze, and publish non-binding recommendations on KIPs. They should "speak for the protocol," rather than their own interests, and be knowledgeable about the subjects being considered. 

Their role is to ensure that every KIP has been given adequate attention before it is put in front of tokenholders for a vote, and that tokenholders are provided with the opinion of qualified stakeholders in case they cannot judge for themselves.

### Sophon onboarding process 

This section defines a process for onboarding one or more Sophons. 

Use the template located at [KIP-0-T1.md](./KIP-0-T1.md).

### Sophon offboarding process 

This section defines a process for offboarding one or more Sophons.

Use the template located at [KIP-0-T2.md](./KIP-0-T2.md)


