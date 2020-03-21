# JumpList_Lnk_Parser
Parser for both JumpList and Lnk files artifacts


# Description
### JumpList: 
The jump list store the recently opened files by application in taskbar
### Lnk Files:
An LNK file is a shortcut or "link" used by Windows as a reference to an original file, folder, or application.

# Analysis
The JumpList and Lnk files indeicate the user acitivies on the machines, for example is user opened word document recently and stored in the JumpList, it will show the path of that document

# Usage
```
usage: Python script parser JumpList and Lnk Files (automaticDestinations-ms, customDestinations-ms, and .lnk)
       [-h] (-f INPUT_FILE | -d INPUT_DIR) [-of OUTPUT_FORMAT]
       [-o OUTPUT_FILE] [-a APPIDS_FILE] [-dl DELIMITER] [-p] [-q]

optional arguments:
  -h, --help         show this help message and exit
  -f INPUT_FILE      Path to the JumpList or Lnk file
  -d INPUT_DIR       Path to the JumpList and Lnk directories (recursively),
                     it will parse all files (automaticDestinations-ms,
                     customDestinations-ms, and .lnk)

Optional Arguments:
  -of OUTPUT_FORMAT  Output format (csv, json), (default: json)
  -o OUTPUT_FILE     Output file to write the results to
  -a APPIDS_FILE     AppIDs configuration file (default: JLParser_AppID.csv)
  -dl DELIMITER      CSV file delimiter (default ",") only if "-o csv" used
  -p                 Save the output of json in pretty format (default: not
                     pretty), only if "-o json" used
  -q                 Don't show the information messages, only the results
```

To avoid printing the error messages and logo use "-q", also make sure to add either file "-f" or directory "-d"


### Output
The output will be stored by default as json format, you can specify the output format by "-of \[csv|json\]", the fields are unified for both JumpList and Lnk files, so it will be in one output file, the field "Artifact" specify whether it is Lnk_File or JumpList

#### Output Fields 
```
LNK_Class_ID
Data_Flags
File_Attrbutes
Time_Creation
Time_Access
Time_Modification
FileSize
IconIndex
ShowWindow
Header_Size
Location_Flags
Drive_Type
Drive_SN
Volume_Label
Local_Path
Network_Share_Flags
Network_Share_Name
Network_Device_Name
Network_Providers
Network_Share_Name_uni
Common_Path
entry_number
AppID
AppType
AppDesc
Source_Name
Source_Path
Artifact
```

# Helpful References: 
https://cyberforensicator.com/wp-content/uploads/2017/01/1-s2.0-S1742287616300202-main.2-14.pdf
https://github.com/libyal/liblnk/blob/master/documentation/Windows%20Shortcut%20File%20(LNK)%20format.asciidoc
https://community.malforensics.com/t/list-of-jump-list-ids/158
