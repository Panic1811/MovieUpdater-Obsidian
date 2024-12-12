# MovieUpdater Plugin Documentation

---

## **Overview**
The `MovieUpdater` plugin is a custom Obsidian plugin designed to fetch movie or series metadata from the OMDb API and update it in your Obsidian notes. It updates both frontmatter fields and note content fields dynamically based on user-defined settings.

---

## **Features**
1. Fetch movie/series metadata from the OMDb API.
2. Update frontmatter fields (YAML section).
3. Update note content fields (outside frontmatter).
4. Fully customizable:
   - Add, remove, or modify fields to update.
   - Dynamically set folder paths for movies and series.
5. OMDb API key support.
6. Works across multiple vaults (by copying the plugin folder).
7. Includes a user-friendly settings panel for managing fields and folders.

---

## **Installation**
### **Initial Setup**
1. Clone or download the `MovieUpdater` plugin source.
2. Run `npm run dev` to build the plugin for the first time.
3. Move the `MovieUpdater` folder into `.obsidian/plugins` of your vault.
4. Enable the plugin in `Settings > Community Plugins`.

### **For Additional Vaults**
1. Copy the `MovieUpdater` folder (from `.obsidian/plugins` in the original vault).
2. Paste it into the `.obsidian/plugins` folder of the new vault.
3. Enable the plugin in the new vault.

---

## **How It Works**
The plugin fetches metadata from OMDb based on the note title (specified in the `title` field in frontmatter) and updates:
- **Frontmatter fields:** Key-value pairs in the YAML section.
- **Note content fields:** Text fields outside the YAML, formatted based on user-defined labels.

---

## **Configuration**
The settings panel allows customization of:
1. **OMDb API Key**: Used for accessing OMDb metadata.
2. **Folders**:
   - Define the folders containing movie or series notes.
   - Supports dynamic folder paths.
3. **Frontmatter Fields**:
   - Define which YAML fields to update and their corresponding API results.
4. **Note Content Fields**:
   - Define labels for note content fields and their corresponding API results.

---

## **Settings Panel**
### **Main Panel**
- **OMDb API Key**: Enter the API key for OMDb.
- **Folder Paths**: Add or remove folder paths for movies and series notes.
- **Field Previews**:
  - View current frontmatter and note content field mappings.
- **Edit Buttons**:
  - Open modals to customize frontmatter or note content fields.
- **Documentation Link**:
  - A quick link to the plugin's documentation.

### **Modals (Field Management)**
1. **Frontmatter Fields**:
   - Specify YAML field names and corresponding OMDb API results.
   - Add or remove fields dynamically.
2. **Note Content Fields**:
   - Specify labels (e.g., `**Director:**`) and corresponding OMDb API results.
   - Add or remove fields dynamically.

---

## **Key Code Details**
### **OMDb API Integration**
- Fetches metadata using the `fetchMovieData()` method.
- Supports separate handling for movies (`type=movie`) and series (`type=series`).
- Key fields like `BoxOffice`, `RT`, `imdbRating`, and `Awards` are parsed and formatted dynamically.

### **Formatting Adjustments**
- **Rotten Tomatoes (RT):** Reformatted to display as `Rotten Tomatoes: 92%`.
- **Box Office:** Automatically removes unnecessary formatting.

### **Dynamic Updates**
- Only updates fields specified in the settings.
- Avoids overwriting fields not present in the note.
- Ensures compatibility with existing templates.

---

## **Adding New API Fields**
1. Open `ManageFieldsModal.ts`.
2. Add the desired API result to the `availableApiFields` array.
3. Open the plugin settings in Obsidian.
4. Add the new field in the Frontmatter or Note Content modals.

---

## **Troubleshooting**
1. **Fields Not Updating:**
   - Ensure the API result matches OMDb's response fields.
   - Verify the note title matches the movie/series title on OMDb.

2. **Plugin Errors:**
   - Check the Obsidian console (`Ctrl+Shift+I`) for logs.
   - Ensure all folders in the settings exist.

3. **Field Duplication in Notes:**
   - Ensure note content labels are unique in the note.

---

## **FAQs**
### **Q: Can I use this plugin across multiple vaults?**
A: Yes, copy the `MovieUpdater` plugin folder into the `.obsidian/plugins` folder of the target vault.

### **Q: How do I add a new field from OMDb?**
A: Add the field in the settings modals or update `ManageFieldsModal.ts` to include it.

### **Q: What happens if a field is not found in OMDb?**
A: The field is skipped during updates, ensuring no overwrites or errors.

---

## **Future Improvements**
1. Support for multiple API providers.
2. Customizable templates for note formatting.
3. Advanced error handling and validation.

---

## **License**
This plugin is open-source and free to use. Contributions are welcome.
