# Testing with Ephemeral Environments

This project was created to illustrate what an **ephemeral testing environment** is and how it is different from traditional development, quality assurance/stage, and production environments. In short, ephemeral environments live for as long as it takes to execute the tasks they are responsible and then they die. Eternal environments (like DEV, QA, and PROD) live for the life of the application development and support cycle.

![](https://i.imgur.com/nd37ZlZ.png)

Ephemeral testing environments are isolated containers that are initialized—"spun up"—based on a specific action to execute specific tasks. After the task is complete, the environment is destroyed. Since we are dealing with testing only here, what we want to do is create an ephemeral environment to run all tests in our sample app to ensure our new code doesn't break any existing functionality. In order to do that, we need **Node 12.x** installed in the ephemeral environment. We will use **Ubuntu** for the OS.

In order for our tests to run properly, we need to install the dependencies of our application which are managed via NPM. Given that our ephemeral environment will support Node globally, we can simply run

`npm install`

and once complete, run

`npm test`

This will run all of the tests in our application to determine whether or not our code can be merged. If any test fails, the pull request will not be mergeable. Developers will be able to see what specific test(s) failed and why. If all the tests pass and the branch is up-to-date, the pull request can be merged.

## Our Sample Workflow

![](https://i.imgur.com/4LJa9YN.png)

![](https://i.imgur.com/lQlfjls.png)

![](https://i.imgur.com/4umumF0.png)

<br>
<br>

# Developer Insights

There are a variety of insights that are exposed to developers through this process:

1. See what tests ran
2. See what tests failed
3. See what tests passed
4. See if their application code needs to be updated or their test code needs to be updated (or both)
5. See whether their code is the culprit or whether a dependency failed to install (or something else entirely)
6. Determine better pre- and post-PR workflow

<br>

## <span style="color:darkred">Failure Example </span>

![](https://i.imgur.com/2N3jZMu.png)

![](https://i.imgur.com/q4pokAO.png)

<br>
<br>
<br>
<br>

## <span style="color:darkgreen">Success Example</span>

![](https://i.imgur.com/JNnLghL.png)

![](https://i.imgur.com/QuLy69S.png)
