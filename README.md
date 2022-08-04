history-archiver
================

A project to backup historical data.  

Subsets of 'ineoall' tables 'ms_history_no_null_DO_NOT_REMOVE' and 'cdvr_history_no_null_DO_NOT_REMOVE' on the 'db4' server are backed up to flat files using this script.  

Monthly data is divided into thirds, 1-9, 10-19, 20-XY. This script will operate on the last full data set available.  

Currently, the script is executed manually.  

As an example, 'MS_JAN1_2015' and 'CDVR_MS_JAN1_2015' tables are created on the 10th for data from the 1st through the 9th.  

The tables are dumped, zipped, & copied to conf.BACKUP_HOST before they are dropped.  

*_JAN2_2015 would account for the 10th through the 19th, and *_JAN3_2015 would account for the 20th through the last day of the month.  

This should not be run on weekends or while the daily processing is still running (after ~12PM ET).  

Historical data needs be backed up for two years, though a mechanism for deleting data has not yet been automated.
