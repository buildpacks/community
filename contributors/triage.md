# Triage

Triaging is the act of managing issues, determining the appropriate response, and following up with the original poster to ensure the problem was solved.

### Actionable Issues

An actionable issue is one that can be worked on, such that the following is true:

- A definition of done is provided - whether that is formal acceptance criteria or clear expectations.
- Appropriate label(s) is present on the issue
    - `type/*`
    - `size/*` (if possible)
    - `status/ready`
    - `good first issue` (if applicable, see [Good First Issues](#good-first-issues))

### Good First Issues

Good first issues, are issues which new contributors can relatively easily pick up. Keep in mind that new contributors likely will not have the context you do. They should be as discriptive as possible and provide good formal acceptance criteria, preferably in [gherkin](https://cucumber.io/docs/gherkin/reference/). By providing acceptance criteria, it makes it easier for newer contributors to understand all the inputs and outputs to setup a good test scenario.

Example of a good first issue:

> Title: Create a new good first issue
>
> Description:
>
>     ### Summary
> 
>     As a project contributor, I would like to create an issue that new contributors can pick up.
> 
>     ### Acceptance Criteria
>
>     ```gherkin
>     Given I have permissions to add labels
>     When I create a good first issue
>     Then the issue should have the label "good first issue"
>     And the issue should have at least 1 Acceptance Criteria
>     ```


### Actions

The following is a flow to assist contributors in assigning the appropriate labels to an issue.

- Is this a support request?
    - Yes
        - Add label `type/support`
        - Provide support and close the issue with label `status/resolved`\
          OR 
        - Request further information from the issue author and label `status/needs-information`
        - If activity is missing for 10 days, follow up
        - If activity is missing for 30 days, close
    - No
        - See below
- Is this something we want to do?
    - I don’t even understand this issue
        - Remove label `status/triage`
        - Add label `status/needs-information`
        - Comment in request for clarification
        - If activity is missing for 10 days, close
    - No - not valid / relevant for our project
        - Remove label `status/triage`
        - Add label `status/invalid`
        - Comment and close
    - Maybe - needs RFC
        - Remove label `status/triage`
        - Add label `status/requires-rfc`
        - Comment on suggestion for RFC
        - If no further activity for 10 days, close
    - Maybe - needs alignment
        - Remove label `status/triage`
        - Add label `status/discussion-needed`
        - Add appropriate `type/*`
    - Maybe - I can’t tell from the information in the issue
        - Remove label `status/triage`
        - Add label `status/needs-information`
        - Request further information from issue author
        - If no further activity for 10 days, close
    - Yes
        - Could this be worked on right now?
            - Yes
                - Remove label `status/triage`
                - Add label `status/ready`
                - Add appropriate `size/*` (if possible), `type/*`, and `good-first-issue` if it is relatively straightforward
            - Sort of - requires additional research
                - Remove label `status/triage`
                - Add label `status/ready`
                - Add label `type/research`
                - Comment on what information we need from the research task. Outcome of research should yield new issue or close this issue.
            - No - needs clearer definition of done
                - Remove label `status/triage`
                - Add label `status/needs-information`
                - Add appropriate `size/*` (if possible) and `type/*`
                - If activity is missing for 10 days, follow up 
                - If activity is missing for 30 days, close 
            - No - needs alignment
                - Remove label `status/triage`
                - Add label `status/discussion-needed`
                - Add appropriate `size/*` (if possible) and `type/*`
            - No - blocked by other work
                - Remove label `status/triage`
                - Add label `status/blocked`
                - Add appropriate `size/*` (if possible) and `type/*`
