# Practice Task: Create Team Members View Display
## Objective
Create a custom content type for team members and build a paginated view to display them with filtering and sorting capabilities.

## Requirements

### Content Type Setup
Create a new content type called "Team Member" with the following fields:
- Title (default) - Used for member's full name
- Profile Image (Media)
- Position (Text)
- Department (Term reference)
- Email (Email)
- Bio (Long text)
- Social Media Links (Link - Multiple)
- Hiring Date (Date)
- Featured Member (Boolean)
- Skills (Term reference - Multiple)

### Taxonomy Setup
Create two vocabularies:
- Departments
    - Add terms: Engineering, Marketing, Sales, Management, HR
- Skills
    - Add sample skills: Drupal, PHP, JavaScript, Project Management, etc.

## Views Requirements
### Main View Configuration
- View Name: Team Members Directory
- Machine Name: team_members_directory
- Show: Content of type Team Member
- Page Display: /team-members
- Items per page: 9
- Use AJAX: Yes

### Required Displays
- Page Display (Grid)
    - Path: /team-members
    - Display format: Grid
    - Columns: 3 (responsive)
- Block Display (Featured Members)
    - Display format: List
    - Limited to 3 items
    - Show only featured members

### Fields to Display
- Profile Image
- Full Name (Title)
- Position
- Department
- Email
- Skills (as tags)
- Hiring Date (formatted as 'time ago')

### Filter Criteria
Exposed filters for:
- Department (Dropdown)
- Skills (Multiple select)
- Hiring Date (Date range)

### Sort Criteria
- Default sort: Hiring Date (DESC)
- Exposed sort options:
    - Name (A-Z)
    - Hiring Date
    - Department

### Additional Features
- Add a views header with total results count
- Add a custom "No results" behavior
- Implement AJAX-based pager

# Installation instructions

1. Install WSL and Docker
2. Run this command in your Linux terminal to install DDEV:
`curl -fsSL https://raw.githubusercontent.com/ddev/ddev/master/scripts/install_ddev.sh | bash`
3. Run these commands to create and start a new drupal project:
`mkdir my-drupal-site && cd my-drupal-site`
`ddev config --project-type=drupal10 --docroot=web`
`ddev start`
`ddev composer create drupal/recommended-project:^10`
`ddev composer require drush/drush`
`ddev drush site:install --account-name=admin --account-pass=admin -y`
`ddev launch`
`# or automatically log in with`
`ddev launch $(ddev drush uli)`
4. If your terminal can't find a browser you can set it by adding this line to ~/.bashrc (may require restart):
`export BROWSER="powershell.exe /C start"`
5. Import the config files using Drush
