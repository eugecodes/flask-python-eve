# twisted-dragon
This project aims at aggregating data from varied sources

Technologies
Python v.3+, necessary modules are listed in requirements.txt. Currently the web framework is not used; the scripts can be run using cron job on the required schedule (e.g. once in 3 month).

Notes on the implemented functionality
Importing the data for all available years - script import_all.py 

Updating the values for the last 5 years - script update_all.py 

Import implementation

Data is being imported in 10 threads. The app imports only data that is not empty (i.e. indicators values that are empty will not be saved into the DB). Values that have invalid format (e.g. if "Period 2008-2010" is returned as a date) are also skipped.

 If the service returns an error, the app will retry 3 times. If these attempts are not successful, the request is skipped.

After the import is complete, the log file with details on the import process and errors will be emailed to the address specified in the config (see details below).

Config file
Configuration file config.py contains the following settings

DEBUG = True - logging level. 'False' value should be used if only errors are to be logged.
SQLALCHEMY_DATABASE_URI - DB connection string.
DATA_IMPORT_YEARS - for how many years back will we request the info from the API (used in the update_all.py).
EMAIL - email settings (ALLOConfiW, FROM, TO, SUBJ, SERVER_SMTP, SERVER_PORT, SERVER_USER, SERVER_PASS - the meaning of each individual parameter is described in the file itself).
 
