Generate a feature spec and write it under .ai/specs folder for the following: $ARGUMENTS
generate the name base simple as possible


Use this exact structure:

---

# Title
A clear, concise name for the feature.

## What
Describe what this feature does and why it exists. Include the problem it solves and the expected outcome from a user or system perspective.

## Constraints

**Do:**
- List what must be done or followed

**Don't:**
- List what must be avoided or is out of scope

## Tasks
Break the feature down into concrete, actionable development tasks. Each task should be small enough to implement and verify independently.

# Task 1
# Task 2
# ...

---

Keep the spec implementation-agnostic where possible. Focus on what needs to be built, not how. Reference the relevant Strimops component (translator, strimops-helm, strimops-operator) for each task where applicable.
