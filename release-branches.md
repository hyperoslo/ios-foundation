# Release branches

At Hyper, we use release branches to ensure that an upcoming release won't be affected by rapid development on the `master` branch.

We do this rather than using long-lived feature branches, which are painful for a couple of reasons:

- They tend to be hard to merge back in to `master`, since both the feature branch and the `master` branch move quickly, resulting in a significant separation of the code base.
- They are harder to manage, since we have to keep track of multiple branches, some of which might be outdated and abandoned.
- They add risk and Q&A work since the app's state is different in each feature branch.

Our workflow is as following:

- When a new release candidate is going to be made (which is usually the point at which we distribute a build locally inside Hyper, or to the customer, through Crashlytics/TestFlight) - `master` is branched off into `release/current`.
- `release/current` will live as long as the release hasn't been released. If bug fixes need to be made for the release, those are targeted against the `release/current` branch.
- All "normal" work, not related to the release, continue on `master`, just as before.
- Once the release has been finalized (most likely published to the App Store), the current state of `release/current` is `git tag`-ed as `release/<version-number>`.
- `release/current` is then merged back into master, and the `release/current` branch is deleted.
