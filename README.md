# Veracode Bulk User Creator/Editor

## Overview

This script allows for bulk modifying and/or creating users in Veracode.

## Installation

Clone this repository:

    git clone https://github.com/cadonuno/Veracode-Bulk-User-Management.git

Install dependencies:

    cd Veracode-Bulk-User-Management
    pip install -r requirements.txt

### Getting Started

It is highly recommended that you store veracode API credentials on disk, in a secure file that has 
appropriate file protections in place.

(Optional) Save Veracode API credentials in `~/.veracode/credentials`

    [default]
    veracode_api_key_id = <YOUR_API_KEY_ID>
    veracode_api_key_secret = <YOUR_API_KEY_SECRET>


### Preparing the Excel Template
    The Excel template present in the repository can be used to prepare the metadata. After the script finishes execution,
    a new column will be added to the right containing the status of each line
    
### Running the script
    py bulk-user-management.py -f <excel_file_with_user_information> [-c] [-d]
        Reads all lines in <excel_file_with_user_information>, for each line, it will modify the user profile
        If a field is left empty, it will not be modified, to clear assigned teams, set the value to NONE (case sensitive). 
        If a team does not exist, it will be created.
        To create new users, you can pass the -c flag.

If a credentials file is not created, you can export the following environment variables:

    export VERACODE_API_KEY_ID=<YOUR_API_KEY_ID>
    export VERACODE_API_KEY_SECRET=<YOUR_API_KEY_SECRET>
    python bulk-user-management.py -f <excel_file_with_user_information> [-c] [-d]

## License

[![MIT license](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

See the [LICENSE](LICENSE) file for details
