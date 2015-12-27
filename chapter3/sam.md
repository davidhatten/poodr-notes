##"A class should know just enough to do its job and not one thing more"

- Dependencies are defined as any piece of knowledge a class must know about a collaborator.
- Some degree of dependency is necessary for collaboration. Unecessary dependencies should be eliminated.
- Each dependency creates a chance that a class will be forced to change when it's collaborator changes. Even when that change is unrelated to the collaboration. This turns minor code tweaks into large undertakings where small changes cascasde across the code base.
- Each dependency makes the code less reasonable.

# Writing Loosely Coupled Code

**Inject collaborators to eliminate the implementation type dependencies**

Deep declaration of dependency implementation eliminates your option to use a different type with the same contract. You are forced to always use that implementation. This is especially a problem in tests, and leads to a desire for partial or over mocking. Both increase coupling and fragility in test code.
