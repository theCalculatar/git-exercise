Git-Flow Exercise with Back-Merge
Scenario
The team is building a "Team Goals Tracker" application. 

Each developer has been assigned a specific feature and needs to complete this and have it merged into main for it to be deployed.
Steps
Step 1: Cloning and Branch Setup
1. Learners clone the repository and switch to the develop branch:
git clone [<repository-url>](https://github.com/The-DigitalAcademy/git-exercise)
cd team-goals-tracker
git checkout develop
2. Each learner creates a feature branch for their assigned task:
git checkout -b feature/<feature-name>
Example feature names:
- feature/add-goal
- feature/edit-goal
- feature/delete-goal
- feature/view-goal
- feature/user-auth

Step 2: Implementing Features
1. Learners edit the app.goals.txt file to implement their features:
Team Goals Tracker - Features
------------------------------
- Add Goal: Allows users to add new goals to the tracker.
- Edit Goal: Enables modification of existing goals.
- Delete Goal: Removes unwanted goals from the tracker.
- View Goal: Displays all active goals in a list format.
- User Authentication: Ensures only registered users can access the tracker.
2. Learners commit and push their changes:
git add app.goals.txt
git commit -m "Implemented <feature-name> functionality"
git push origin feature/<feature-name>
Step 3: Pull Requests and Back-Merge
1. Each learner creates a pull request (PR) to merge their feature branch into develop on GitHub.
2. The Team Leader reviews and merges the PRs into develop.
3. Back-Merge Step:
   After a PR is merged, all other developers pull the updated develop branch into their feature branches:
git checkout feature/<feature-name>
git pull origin develop
This keeps their branches updated with the latest changes from the team.
Step 4: Introducing a Merge Conflict
1. After Learner 3 (Delete Goal) creates their PR, Learner 1 (Add Goal) makes a direct change to the app.goals.txt file in the develop branch:
- Add a placeholder line in the "Delete Goal" section:
- Delete Goal: Placeholder text for Delete Goal functionality.
git checkout develop
git add app.goals.txt
git commit -m "Added placeholder for Delete Goal"
git push origin develop
2. Learner 3 pulls the updated develop branch into their feature branch:
git checkout feature/delete-goal
git pull origin develop
3. Git reports a merge conflict in app.goals.txt.
Step 5: Resolving the Conflict
1. Learner 3 resolves the merge conflict manually by keeping the intended content in app.goals.txt:
- Delete Goal: Removes unwanted goals from the tracker.
2. Mark the conflict as resolved and commit:
git add app.goals.txt
git commit -m "Resolved merge conflict for Delete Goal feature"
3. Push the resolved changes back to the feature branch:
git push origin feature/delete-goal
4. The Team Leader reviews and merges the updated PR into develop.
Step 6: Final Merge to Main
1. Once all feature branches are merged into develop, the Team Leader merges develop into main:
git checkout main
git merge develop
git push origin main
Wrap-Up Discussion
1. Back-Merge Importance:
- Reinforce the need to keep feature branches in sync with develop.
- Highlight how back-merging reduces the likelihood of large-scale merge conflicts later.
2. Merge Conflicts:
- Discuss why conflicts arise and how to resolve them efficiently.
3. Git Flow Advantages:
- Emphasize how the workflow ensures structured development and collaboration.