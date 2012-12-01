Rally Build Traceability
============

![Title](https://raw.github.com/RallyApps/BuildTraceability/master/screenshots/title-screenshot.png)

## Overview

The Build Traceability app provides a view of Rally work items (user stories, defects, and tasks) that have been assigned to a particular build.

## How to Use

### Running the App

If you want to start using the app immediately, create an Custom HTML app on your Rally dashboard. Then copy App.html from the deploy folder into the HTML text area. That's it, it should be ready to use. See [this](http://www.rallydev.com/help/use_apps#create) help link if you don't know how to create a dashboard page for Custom HTML apps.

Or you can just click [here](https://raw.github.com/RallyApps/BuildTraceability/master/deploy/App.html) to find the file and copy it into the custom HTML app.

### Using the App

The workflow for this app begins with a developer including information on the Rally work item Formatted ID field (in a commit message), to create an association between the changeset and work item. The changeset object is created by the Rally Source Code Management connectors. The commit then triggers a Jenkins continuous build. Once the Jenkins continuous build completes, a post-build step using the [Rally Connector for Jenkins](http://www.rallydev.com/help/jenkins) will create a build object in Rally that is associated with the changeset.

## Customize this App

<b>NOTE:</b> This app doesn't work using just App-debug.html. In BuildTraceability.js on the buildProjectQuery() function, you need to add in a list of project oids manually.

You're free to customize this app to your liking (see the License section for details). If you need to add any new Javascript or CSS files, make sure to update config.json so it will be included the next time you build the app.

This app uses the Rally SDK 1.32. The documentation can be found [here](http://developer.rallydev.com/help/app-sdk). 

Available Rakefile tasks are:

    rake build                      # Build a deployable app which includes all JavaScript and CSS resources inline
    rake clean                      # Clean all generated output
    rake debug                      # Build a debug version of the app, useful for local development
    rake deploy                     # Deploy an app to a Rally server
    rake deploy:debug               # Deploy a debug app to a Rally server
    rake deploy:info                # Display deploy information
    rake jslint                     # Run jslint on all JavaScript files used by this app, can be enabled by setting ENABLE_JSLINT=true.

## License

BuildTraceability is released under the MIT license. See the file [LICENSE](https://raw.github.com/RallyApps/BuildTraceability/master/LICENSE) for the full text.