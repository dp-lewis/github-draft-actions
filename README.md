# github-draft-actions

This repository demonstrates how to trigger GitHub Actions based on different pull request draft states.

## Workflows

This repository contains three workflows that showcase different PR scenarios:

### 1. PR Opened as Draft (`pr-opened-as-draft.yml`)
**Trigger:** When a PR is opened in draft mode

**Event:** `pull_request` with type `opened` and condition `draft == true`

This workflow runs when you create a new pull request and mark it as a draft from the start.

### 2. PR Ready for Review (`pr-ready-for-review.yml`)
**Trigger:** When a draft PR is marked as ready for review

**Event:** `pull_request` with type `ready_for_review`

This workflow runs when you convert a draft PR to ready for review by clicking the "Ready for review" button.

### 3. PR Opened Ready (`pr-opened-ready.yml`)
**Trigger:** When a PR is opened directly as ready (not draft)

**Event:** `pull_request` with type `opened` and condition `draft == false`

This workflow runs when you create a new pull request without marking it as a draft.

## Testing the Workflows

To test each workflow:

1. **Test Draft PR Creation:**
   - Create a new branch
   - Open a PR and check "Create as draft"
   - Watch for the "PR Opened as Draft" workflow to run

2. **Test Draft to Ready Conversion:**
   - Use the draft PR from step 1
   - Click "Ready for review" button
   - Watch for the "PR Ready for Review" workflow to run

3. **Test Direct Ready PR:**
   - Create another new branch
   - Open a PR without marking it as draft
   - Watch for the "PR Opened Ready" workflow to run

## Workflow Details

Each workflow:
- Checks out the code
- Prints information about the PR (number, title, author, draft status)
- Includes descriptive messages explaining when it runs

These workflows serve as templates that can be extended with actual CI/CD tasks, notifications, or other automation.