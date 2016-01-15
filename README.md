# Work

Here are a few of the projects and features I have worked on individually or on teams at Mavenlink.

##Mavenlink product support:

 * Implemented a fix to prevent 'read-only' users from replying to a post email. This fix added a forgotten permission check  to a conditional in our mailer.

 ![Support 1]
 (/Support-2.png)

 * Fixed default permission levels for 'Resources' on project create via template.

 * Fixed a bug where, on project creation via applying a template, the user would be redirected to the project home page. The fix for this required passing data through multiple Backbone.Marionette templates.

##[Marketing site](https://www.mavenlink.com)

  * ######JOBVITE INTEGRATION:

    Replaced our current manual via admin panel career creation, and replaced with a Jobvite integration. This integration  works by calling the Jobvite API, and syncing the response with our local database.

    Key files and architecture:

      - JobviteInterface.rb: sets up the jobvite api request and either returns the parsed response or raises an error.
      - JobviteSync.rb: calls the api and syncs our DB with job data from jobvite.
      - jobvite.rake: runs JobviteSync.run nightly in a cron job.
      - admin.js: on click of 'sync jobs' button in admin panel, hits admin/homes/sync action.
      - homes_controller.rb: #sync calls Jobvite.run and rescues if there is an error.

  * ######HOME PAGE REDESIGN:

    ![Mavenlink Homepage]
    (/Mavenlink-Homepage.png)

  * ######PRICING PAGE REDESIGN:


    ![Mavenlink Pricing Page]
    (/pricing.png)

  * ######AB TESTING:
    
   Using Optimizely to determine the most successful of three pricing page variants.
