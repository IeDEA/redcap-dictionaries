# redcap-dictionaries
REDCap Data Dictionaries for IeDEA 
This directory contains REDCap data dictionaries for ongoing IeDEA and Harmonist projects.

## Harmonist Data Model (0A) and Code List Projects (0B)

These REDCap XML data dictionaries can be instantiated on any REDCap installation to create the Data Model and Code List REDCap projects that inform the [IeDEA Data Exchange Standard Website](http://iedeades.org).

Please note that for reusability and compatibility with the XML data dictionary format, the `code_list_ref` variable in the **Harmonist0A: Data Model** project is listed as a plain dropdown variable in the XML for the Harmonist 0A project. In this variable, dropdown codes refer to record IDs in the 0B project, and labels refer to the descriptive names of the code lists.

For users with administrator rights on the REDCap installation, the `code_list_ref` variable should be changed to a **"Dynamic Query (SQL)" field type**, using the SQL listed below, where xxxx represents the project ID number (pid) of the **Harmonist 0B: Code Lists** project. This configuration makes it easier to link variables with code lists, since any code lists newly added to the Harmonist 0B project will be automatically added to the dropdown options in Harmonist 0A.

## SQL
SELECT record, value FROM redcap_data WHERE project_id = xxxx and field_name = 'list_name' ORDER BY value ASC
