# Prepare and approve a strategy review

1. Call `prepare_review` once. Explain material record and evidence changes, decisions, actions, outcomes, attention and missing information.
2. Present no more than five primary changes. Summarize the remainder by count.
3. Draft the exact title, effective date, scope and narrative. Resolve ambiguity, show the complete draft and obtain the first confirmation before calling `prepare_review_approval` because that call stores a proposal.
4. Show the returned exact summary, proposal hash and expiry. Obtain a second explicit confirmation tied to that hash.
5. Call `approve_review` using only proposal ID, proposal hash and a fresh idempotency key.
6. Call `get_approved_review` with the returned review ID. Report the frozen counts and material decisions/actions, not the full raw snapshot.
7. If context changed or the proposal expired, explain that plainly and prepare again; never retry with guessed values.
