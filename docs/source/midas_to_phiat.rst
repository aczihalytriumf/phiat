Overview
-----
* Converts MIDAS files from MPET DAQ to PhIAT-compatible format
* Written in Python
* Input: directory to MIDAS files (.mid.lz4)
   * Example: C:\Users\aczihaly\Documents\PIICR_Analysis\Data\Actual\multiple_consecutive_files
* Output: 
   * .csv files containing position, time-of-flight and TDC trigger information
   * .csv files containing approximate count rates
   * One .csv file containing an address list of converted MIDAS files, their accumulations times (Taccs) and reference files assignments

Initialization
-----
* On Line 20: Change the address in sys.path.append from '/Users/wsporter/Documents/Physics_Research/TITAN/PIICR_Analysis/titan_data' to the local address of titan_data on your computer
   * Download titan_data: https://bitbucket.org/ttriumfdaq/titan_data/src/master/
   * Example: sys.path.append('/Users/aczihaly/Documents/PIICR_Analysis/titan_data')
* all_one_file: 
   * Default is all_one_file = TRUE for PI-ICR analysis 
* CAEN/ VT2: Set TRUE whichever TDC is being used to read out data (indicated in the MPET DAQ under 'Scan')
   * Default is CAEN = TRUE
   *  CAEN and VT2 cannot both be true- this will trigger an error
* testing: If you are using test data from MIDAS that DOES NOT include a reference file (i.e. a Tacc of 0), set to TRUE (automatically assigns the last file a Tacc of 0, as needed to run through the script)
   * Otherwise, set to FALSE (the default for normal data)

Data
-----
4 pieces of information are important:

#. x position (mm)
#. y position (mm)
#. time of flight (s)
    * from extraction to detector
#. trigger (integer) or timestamp (s)
    * CAEN: trigger
       * Trigger number an ion hit came during (starting from 0 at file beginning)
    * VT2: timestamp
       * Timestamp of event relative to initial trigger time
