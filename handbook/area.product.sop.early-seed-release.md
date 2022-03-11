---
id: 27fd4443-58b5-4fdc-a1ca-1aa4ca9f8397
title: Early Seed Release
desc: ''
updated: 1647012057699
created: 1623344680534
---

## Summary
How we handle Dendron's early seed releases

## Steps

### Code

#### Before the release
1. Go to [[Create Release Image|dendron://dendron.handbook/s.github.ref.actions#create-release-image]] github actions and view the latest pipeline run. See [[Pipelines for General Release|dendron://dendron.docs/dev.build.automation#pipelines-for-general-release]] for more info.
1. Check that features in [[Ready to Ship|dendron://dendron.handbook/area.product.concepts.ready-to-ship]] are accurate. 
    - copy the commit id of what was pushed in the latest pipeline run, see [here](https://www.loom.com/i/5e945dfecf4b4ee487a13ec8338f0127) for screenshot
    - look at [commit history](https://github.com/dendronhq/dendron/commits/master) of dendronhq to match last merge changes
    - make sure this is accurate with the latest contents of `Ready to Ship`
        - if not, create a new [[Weekly Journal (Team)|dendron://dendron.handbook/area.product.concepts.weekly-journal-team]]
        - to create a journal, follow same instructions as [[individual weekly journal|dendron://dendron.handbook/handbook.sop.weekly-journal#steps]] but do it for the team weekly journal
        - copy over any of next week items to this journal 
1. Install the .vsix file locally and do a sanity check in `test-workspace` 
    - make sure early seed features from [[Ready to Ship|dendron://dendron.handbook/area.product.concepts.ready-to-ship]] don't have any obvious bugs
    - See [here](https://stackoverflow.com/questions/42017617/how-to-install-vs-code-extension-manually) for how to install `.vsix` manually
    - If a bug is detected, ping `@Dendron Team` and relevant parties to get it fixed 
1. If everything works, add to the release note thread of the week 

### Docs
1. Make sure [[Early Seed Changelog|dendron://dendron.dendron-site/changelog.early-seed]] is updated by following the process [[here|dendron://dendron.handbook/area.product.sop.changelog-update]]. This should be submitted as a PR to `dendron-site`.
1. When the code is ready, merge into master
    ```sh
    git checkout master
    git pull
    git merge dev
    git push
    ```
1. Check that the changes have made it to the main page
1. Use the following template[^1] to write the announcement message
    - You can see an example of a past announcement [here](https://discord.com/channels/717965437182410783/771518214558449685/878434754918228031)
    - see the sop on release highlights [^4] for release format
1. Announce announce the release in the `#environmentalist` channel with the `@Environmentalists` mention.

## Checklist
- code
    - [ ] test early seed build
    - [ ] if any issues detected, check in changes into the `release/*` branch directly

- docs
    - [ ] [[Early Seed Changelog|dendron://dendron.dendron-site/changelog.early-seed]] is updated
      - [[Changelog|dendron://dendron.dendron-site/templates.changelog]]
    - [ ] changelog is published
    - [ ] announcement made
      - [[Discord Announce|dendron://dendron.handbook/area.product.sop.early-seed-release.temp.discord-announce]]
      - Announce in the `#environmentalist` channel

## Templates

- [[Changelog|dendron://dendron.dendron-site/templates.changelog]]
- [[Discord Announce|dendron://dendron.handbook/area.product.sop.early-seed-release.temp.discord-announce]]

### Good Release

Tests run on early seed, we're ready to ship 🌱

## Cook

### Updating early seed build

If you need to update the early seed build with changes that were pushed after the [[Early Seed Release|dendron://private/area.team.ref.schedules.release#early-seed-release]], follow instructions below:

[[Update contents of the release image|dendron://private/area.product.sop.weekly-release.build.v2#update-contents-of-the-release-image]]

## Reference

### Release Schedule 

Refer to the [Dendron Release Google Calendar](https://calendar.google.com/calendar/u/1?cid=Y19jcjFwNnNhOHUzYzgzY2Q4ZTR0dmd1ZHU3NEBncm91cC5jYWxlbmRhci5nb29nbGUuY29t) for times of Notable events such as Branch Snaps, Target Release Times.


[^1]: [[Template|dendron://dendron.handbook/area.product.sop.release-highlights.template]]
[^2]: [[Update Changelog|dendron://dendron.dendron-site/changelog]]
[^3]: [[Team Announce|dendron://dendron.handbook/area.product.sop.early-seed-release.temp.team-announce]]
[^4]: [[Release Highlights|dendron://dendron.handbook/area.product.sop.release-highlights]]