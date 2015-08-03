# 2.0 #
  * Supports all Data Loader versions - no need to download a separate version of CLIq for each version of Data Loader
  * Support for all Data Loader operations including Extract All and Hard Helete
  * Validation of external IDs for upsert
  * Uses Data Loader code for Proxy - reliability should be equal to Data Loader with proxy environments
  * Additional parameters in cliq.properties
  * Eliminated unnecessary libraries - new download is much smaller

# 1.4.19 #
  * Updated for Salesforce API 19.0
  * Fixed Insert option in text ui

# 1.3.18 #
  * Added code for file export rotation in .bat file
  * Updated for Salesforce API 18.0
  * Text UI mode on UNIX fixed.
  * Create a default log-conf.xml which generates runtime sdl.log file under log directory.

# 1.2 #
  * Ensure process name has no numbers for filesystem compatibility
  * Improved Proxy Support
  * Ability to change endpoint (for Sandbox access)

# 1.1 #
  * Add support for UNIX
  * Remove stacktrace if no Internet connection is availble.