# University of Ottawa Creative Writing Club

A website for the University of Ottawa Creative Writing Club (CWC). Provides a hub for users to submit the stories they create during CWC meetings and then share those stories with friends. Furthermore, the website provides a social element, offering methods for users to comment on and critique the submissions of others. Finally, various information regarding the club will be available, including meeting times, the executive members, and other affiliated pages and websites.

## What it needs

* Home page
* Header
* Footer
* Announcements
* Sign up
* Submission page
* Posts
* Search
* Comments
* About / Executive
* User profiles
* Edit profiles

## Pages to create

* Home page
  * Introduction to the website
  * Login
  * Sign up
  * Top
    * Contributors
    * Number of comments on submission
  * Most recent
    * Submissions
    * Comments
    * Users
  * List of themes for semester
* Header
  * Home page
  * Sign up / login / logout
  * Submit
  * Search
  * Profile (when available)
* Footer
  * Meeting times & location
  * Facebook page
* Announcements
  * List of recent announcements
  * Executive posts from Facebook?
* Sign up
  * Username (text field, required)
  * Email (text field, required, @uottawa.ca)
  * Password (password field, required)
  * Confirm password (password field, required)
  * Profile picture (image upload, not required)
  * What do you like to write? (text field, not required)
  * About me (multi line text field, not required)
  * Usage:
    * Must not be logged in (links should be replaced with profile links)
* Submission page
  * Title (text field, required)
  * Tags (with suggestions?)
  * Complete / incomplete (checkbox, required)
  * Body (multi line text field, required) - max length?
  * Save / submit
  * Cancel (go back one page)
  * Usage:
    * Can be used to edit old submissions
      * Clicking 'edit' on a submission (only shown if logged in user is creator) opens the submission page with the content filled, and the id of the story in the url? Pressing save must compare original author and use id in url to save the story
    * Must be logged in to view page
* Posts
  * Title
  * Author
  * Tags
  * Body
  * Submit comment
    * Must be logged in
    * Comment text
  * Comments
* Search
  * Search by tags & title
  * Order alphabetical, by most recent
  * Search submissions or users
* About / Executive
  * Executive members
    * Name
    * Position
    * Brief description
    * Link to profile / submissions
* User profile
  * Username
  * Profile picture
  * About me
  * What do they like to write?
  * Last login date
  * Account creation date
  * Submissions
    * Most recent
    * Most commented
  * Comments
    * Most recent
* Edit profile
  * Load fields from database
  * Profile picture (image upload, not required)
  * What do you like to write? (text field, not required)
  * About me (multi line text field, not required)
  * Change password - Old password, new password, confirm password
  * Save / Cancel
  * Usage:
    * Must be logged in
    * Opens with user's id in url - must validate against logged in user

## Database

* Users
  * Username (string, not null)
  * Email (string, not null, ends in @uottawa.ca)
  * Password (string, not null)
  * Profile picture filehandle (string, optional)
  * About me (string, optional)
  * Preferred mediums / genres (string, optional)
  * Last login date (datetime, not null)
  * Account creation date (datetime, not nul)
  * Id (number, not null)
* Submission
  * Name (string, not null)
  * Date created (datetime, not null)
  * Date modified (datetime, not null)
  * Tags (string, optional)
  * filehandle (string, not null)
  * Id (number, not null)
  * author id (fk, not null)
* Comments
  * author id (fk, not null)
  * submission id (fk, not null)
  * date created (datetime, not null)
  * body (string, not null)
* Tags
  * Id (number, not null)
  * Tag (string, not null)
* UserTags
  * UserId (fk, not null)
  * TagId (fk, not null)
* SubmissionTags
  * SubmissionId (fk, not null)
  * TagId (fk, not null)
