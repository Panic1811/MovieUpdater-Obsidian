# MovieUpdater-Obsidian
Update OMDB API keys in obsidian

MovieUpdater Plugin Documentation
Overview
The MovieUpdater plugin is an Obsidian plugin designed to automatically update frontmatter metadata and note content fields for movies and series using data fetched from the OMDb API. This plugin supports customization of fields, folder paths, and note content formatting through a settings panel.

Installation and Setup
Install the Plugin: Add the plugin files to your Obsidian vault's .obsidian/plugins/MovieUpdater directory.
Build the Plugin:
Run npm install to install dependencies.
Use npm run dev to build the plugin.
Enable the Plugin:
In Obsidian, go to Settings > Community Plugins, enable the plugin, and open its settings panel.
Configure API Key:
Enter your OMDb API key in the OMDb API Key field under settings.
Settings Panel
The settings panel is divided into the following sections:

1. OMDb API Key
Purpose: Enter the API key required to fetch data from the OMDb API.
Location: At the top of the settings panel.
2. Frontmatter Fields
Preview Section: Displays the currently configured frontmatter fields and their associated OMDb API fields.
Edit Button:
Opens a modal to add, edit, or delete frontmatter fields.
Each field has:
Field Name: The frontmatter key (e.g., Box_office, RT).
API Result: The corresponding OMDb API field (e.g., BoxOffice, RT).
A dropdown ensures that only valid OMDb API fields are selectable.
3. Note Content Fields
Preview Section: Displays the currently configured note content fields and their associated OMDb API fields.
Edit Button:
Opens a modal to add, edit, or delete note content fields.
Each field has:
Label: The text label used in the note content (e.g., **Box Office:**).
API Result: The corresponding OMDb API field.
A dropdown ensures that only valid OMDb API fields are selectable.
4. Folder Paths
Purpose: Dynamically specify folders to process for movies and series.
Edit Button:
Allows you to add or edit folder paths for movies and series.
The plugin will only update files within the specified folders.
5. Documentation Link
Purpose: A link to this documentation.
Location: At the bottom of the settings panel.
Functionality
1. Metadata Updates
The plugin fetches data from the OMDb API based on the title field in the file's frontmatter. It updates:

Frontmatter fields: Updates the specified fields in the frontmatter.
Note content fields: Updates or appends specified fields in the note content.
2. Folder-Specific Updates
Files are processed only within the folders specified in the settings panel.
Movies and series have independent folder paths and can be customized.
3. Frontmatter and Note Content Management
If a field is present in the file, it will be updated.
If a field is absent:
Frontmatter: Adds the missing field.
Note content: Appends the field at the bottom of the note.
Supported OMDb API Fields
The following fields are available for use:

Year
Director
Actors
Genre
BoxOffice
RT (Rotten Tomatoes score)
imdbRating
Writer
Awards
Runtime
Code Breakdown
Plugin Files
main.ts:

Contains the core functionality for fetching and updating data.
Defines settings structure and handles metadata updates.
ManageFieldsModal.ts:

Handles modals for editing frontmatter and note content fields.
Provides dynamic dropdowns for selecting OMDb API fields.
Key Methods in main.ts
updateMetadata()

Fetches files from the specified folders.
Extracts the frontmatter and updates metadata using the OMDb API.
updateContent()

Updates or appends fields in both the frontmatter and note content.
fetchMovieData(title: string, isSeries: boolean)

Sends a request to the OMDb API using the provided title.
Differentiates between movies and series based on the folder.
loadSettings() and saveSettings()

Load and save user settings for the plugin.
Key Features in ManageFieldsModal.ts
Field Management:

Add, edit, or remove frontmatter and note content fields.
Dropdown ensures correct OMDb API field selection.
Dynamic Refresh:

Updates the modal in real-time when fields are added or removed.
Formatting Rules
Rotten Tomatoes (RT)
The plugin formats Rotten Tomatoes data to display as:
Rotten Tomatoes: 75%
Box Office
The plugin handles the formatting of box office values (e.g., $108,897,830).
Common Issues
API Key Missing:

Ensure you’ve entered a valid OMDb API key in the settings.
Incorrect Folder Paths:

Verify that the folder paths are correctly configured in the settings.
Field Not Updating:

Ensure the field exists in the OMDb API response.
Check the settings to confirm the field is mapped correctly.
FAQs
Can I use the plugin for files outside the specified folders?

No, the plugin only processes files in the folders specified in the settings.
What happens if a field doesn’t exist in the OMDb API?

The field is skipped without any changes.
Can I reset the settings to default?

Delete the plugin’s settings file in .obsidian/plugins/MovieUpdater/data.json.
Can I customize the note content format?

Yes, you can update the labels and corresponding API fields in the settings panel.
