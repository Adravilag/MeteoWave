# Changelog - 2024-11-08

## Version 1.6.0 - Data Processing and Export Enhancements

### Added
Implemented functionality to export weather data to CSV files based on specified dates.
Developed a method to upload CSV data to MongoDB directly after export.
Enhanced data retrieval with improved handling of locality information from MongoDB.

### Fixed
Resolved date formatting issues in Excel, ensuring that the date in cell F2 displays correctly as DD/MM/YYYY.
Addressed exceptions thrown during the export of data to Excel when community sheets are missing or improperly formatted.

### Changed
Updated the copiar_plantilla method to better handle date formatting in Excel and to ensure data consistency across the application.
Refactored the exportar_datos_a_excel function to include checks for document insertion and overwrite in MongoDB.
Adjusted CSV export functionality to streamline the writing process and ensure proper header alignment.

### Notes
The export and upload processes now include error handling to provide feedback on the success or failure of operations.
Documentation updated to reflect changes in data processing logic and usage instructions for the new export features.


## Version 1.5.0 - Project Architecture Updates

### Added
- Implemented translations for English and Spanish across the application.
- Added weather data processing functionalities with community and date selection options.
- Integrated shapefile data visualization for autonomous communities.

### Fixed
- Resolved issues with button event handling in the GeoPy module.
- Addressed configuration loading for smoother setup across `geo` and `met` arguments.
- Fixed translation loading errors in app_runner.

### Changed
- Minor version updated to support expanded translations and configurable language options.
- Enhanced button creation and event handling in the `geoPy` visualization.
- Refined user prompts for selecting community and data file.

### Notes
- Additional optimizations applied for loading shapefile data and handling errors in missing files.
- Documentation updated for configuration setup and command-line usage instructions.


## Version 1.4.0 - Project Architecture Updates

### Summary of Changes

This update introduces significant modifications to the project structure, dependency management, and automated changelog generation. Below are detailed changes for each relevant file.

### Detailed Changes by File

#### `.gitignore`
- Added `temp` to exclude temporary files from version control.
- Adjusted the `__pycache__` entry to improve handling of Python cache files.

#### `bin/scripts/generate_changelog.py`
- **New file**: Created `generate_changelog.py` in the `bin/scripts/` directory to automate changelog generation.
- **Key functionalities**:
  - Extraction of recent commits from the repository using `git log`.
  - Retrieval of differences in each commit using `git diff`.
  - Generation and storage of a detailed Markdown file documenting changes.

#### `README.md`
- Updated documentation to reflect changes in the project structure and new automation scripts.
- Added details on environment configuration and the use of the changelog generation script.

#### `src/core.py`
- Refactored to improve modularity and facilitate interaction between modules.
- **New functions**:
  - `menu_principal()` to organize user navigation through various application options.
  - `seleccionar_comunidad()` added to allow dynamic selection of the autonomous community.

#### `config/config.json`
- Updated default configurations.
- **New parameters added**:
  - `language`: Defines the interface language.
  - `api_settings`: Contains configurations for interaction with the Open-Meteo API, such as `base_url` and `daily_params`.

#### `.github/workflows/ci.yml`
- Modified CI/CD workflow steps to integrate unit and integration tests.
- **Key changes**:
  - Removed redundant steps.
  - Updated Python version used in tests.
  - Improved setup steps for dependency installation and test execution.

#### `MeteoWave_License.txt`
- Updated license to reflect the current project version.
- Resolved version conflicts within the license file.

### Error Handling Improvements
- Added exception handling in multiple parts of the code to manage common errors, such as missing configuration files or HTTP request failures.

### General Refactoring
- Restructured directories for better project organization.
- Modularized code in `core.py`, `data_acquisition.py`, and `data_processing.py` to enhance maintainability and scalability.

---

**Note:** This update marks a significant milestone in the evolution of **MeteoWave**, focusing on automation and continuous improvement of integration and deployment processes, as well as better project organization to facilitate future expansions and collaborations.