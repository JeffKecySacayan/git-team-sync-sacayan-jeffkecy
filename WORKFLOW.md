\# Git Team Sync Workflow - sacayan.jeffkecy



1\. What did the rejected push error message tell you, and why did it happen?

What it said: The message stated that updates were rejected because the remote repository contained work that you did not have locally ((fetch first)), instructing you to integrate remote changes before pushing again.



Why it happened: It occurred because another clone or teammate had already pushed changes to the same branch on GitHub, causing your local branch to fall behind the remote tip.



2\. What's the actual difference between how you resolved Task 3 (merge) vs Task 4 (rebase)?

Task 3 (Merge): We integrated changes using a standard merge (git pull / git merge), which combined the diverging histories by creating a dedicated merge commit, preserving the exact chronological branching structure.



Task 4 (Rebase): We used git rebase, which lifted our local commits off the old base, applied the new remote commits first, and then re-played our local commits right on top. This resulted in a clean, linear history without a cluttering merge commit.



3\. What one habit would have avoided both rejected pushes in this lab?

Running git pull (or git fetch) to sync with the remote repository before starting new work or attempting to push.



4\. Which approach — merge or rebase — would you default to on a shared team branch, and why?

Default choice: Merge. On a shared team branch (like main or a collaborative feature branch), git merge is safer because it preserves a transparent, immutable history of integrations. Rewriting history via rebase on public branches can disrupt teammates and cause sync conflicts. Rebase is best reserved for cleaning up local, unpushed work.

