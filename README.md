# Linc Demo

This is a demo repository to show off some of the functionality of Linc. The corresponding page in Linc is at: https://app.linc.sh/sites/zetta-demo

This repository is already configured properly, so no more set up is required. Configuration is a step that usually takes about 10-30 minutes for most regular setups. 

The demo is an application that retrieves all images from a subreddit.

# Demo steps

## Step 1: Check out preview links.

One of the core features of Linc is to provide teams with a preview link for every commit against every backend. In this demo we have simulated that by making the subreddit configurable. In a real application you would make things like API urls, and api keys for services like Stripe, Sentry and Rollup configurable.

We have already configured a Cats environment that retrieves the images from the CatsGifs subreddit. You can add any other you want on https://app.linc.sh/sites/zetta-demo/environments.
On https://app.linc.sh/sites/zetta-demo you can click any of the preview links to be taken directly to the preview link against that backend.

## Step 2: Make a change & see Github + Slack integration

If you want to configure Slack integration you can go to https://app.linc.sh/sites/zetta-demo/settings/integrations#slack and install Slack and select a channel to push updates to. Alternatively, here is what an update [looks like](https://raw.githubusercontent.com/bitgenics/zetta-demo/master/Slack_integration.png)

Next up is making a change. Go to `src/App.js` and click `edit`. It is the pencil in the top right corner. [(image)](https://raw.githubusercontent.com/bitgenics/zetta-demo/master/Screenshot_20191101_202353.png)
Above line 27 insert `transform: "rotate(180deg)",` (image)
And when you save, make sure you commit it to a branch, such as `flipped_gifs`. [(image)](https://raw.githubusercontent.com/bitgenics/zetta-demo/master/Screenshot_20191101_202516.png)

If you go to https://app.linc.sh/sites/zetta-demo, the commit should be picked up by Linc and is already building it.

One it is finished you should see a message in your Slack channel with the build and preview information.

If you now create a pull request on the main screen you will be taken to the Pull Request screen. And here you will see a comment from Linc with all the preview links in there.
One of the things we are doing is making sure all the information is pushed out to where people already are, rather than forcing them to dig around for it in multiple tools.

## Step 3: See the feedback extension in action

The next feature we want to show off is our beta feedback tool. If you install the [Linc Chrome extension](https://chrome.google.com/webstore/detail/linc-feedback/hepgmgeaphkfkocdjbanggnnldlbaakm) it will pop up a Linc logo on every preview link you are. And if you click on it it will give you a form to fill out with name and comment and it will upload that feedback comment with a screenshot and other browser data and send that straight to Linc and the relevant Pull Request in Github.

Here is an [image of the feedback tool](https://raw.githubusercontent.com/bitgenics/zetta-demo/master/Screenshot_20191101_202755.png)

## Step 4: Releasing

We haven't enabled production releases, but if we would have all it would take to release the change you made earlier is a merge to master and it would be available to your customers in seconds.
