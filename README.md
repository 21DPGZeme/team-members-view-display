# Practice Task: Create Team Members View Display
Objective
Create a custom content type for team members and build a paginated view to display them with filtering and sorting capabilities.
Requirements

Content Type Setup
Create a new content type called "Team Member" with the following fields:

Title (default) - Used for member's full name
Profile Image (Media)
Position (Text)
Department (Term reference)
Email (Email)
Bio (Long text)
Social Media Links (Link - Multiple)
Hiring Date (Date)
Featured Member (Boolean)
Skills (Term reference - Multiple)

Taxonomy Setup
Create two vocabularies:

Departments

Add terms: Engineering, Marketing, Sales, Management, HR

Skills

Add sample skills: Drupal, PHP, JavaScript, Project Management, etc.

Views Requirements
Main View Configuration

View Name: Team Members Directory
Machine Name: team_members_directory
Show: Content of type Team Member
Page Display: /team-members
Items per page: 9
Use AJAX: Yes

Required Displays

Page Display (Grid)

Path: /team-members
Display format: Grid
Columns: 3 (responsive)

Block Display (Featured Members)

Display format: List
Limited to 3 items
Show only featured members

Fields to Display

Profile Image
Full Name (Title)
Position
Department
Email
Skills (as tags)
Hiring Date (formatted as 'time ago')

Filter Criteria
Exposed filters for:

Department (Dropdown)
Skills (Multiple select)
Hiring Date (Date range)

Sort Criteria

Default sort: Hiring Date (DESC)
Exposed sort options:

Name (A-Z)
Hiring Date
Department

Additional Features

Add a views header with total results count
Add a custom "No results" behavior
Implement AJAX-based pager

