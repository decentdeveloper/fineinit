**File-Integrity-Monitoring-System**

**Project Overview**
The File Integrity Monitoring System (FIMS) is designed to ensure the integrity and security of files within a designated directory by utilizing cryptographic hashing. The system offers two main functionalities: collecting a baseline hash of the files in the target directory and continuously monitoring the files against this baseline to detect any changes, additions, or deletions. This proactive approach helps in identifying unauthorized changes to files, which is critical for maintaining system security and integrity.

**Objectives**
Collect Baseline: Generate a baseline of cryptographic hashes for all files within a specified directory. This baseline serves as a reference point for future integrity checks.
Monitor Files: Continuously monitor the files in the specified directory against the saved baseline. The system will detect and alert the user of any new files, modified files, or deleted files.
**Features**

  **Baseline Collection:**
  
  Compute the SHA-512 hash for each file in the target directory.
  Store the file paths and their corresponding hashes in a baseline file (baseline.txt).
  Ensure the baseline file is updated whenever a new baseline is collected, deleting any existing baseline file beforehand.
		
  **File Monitoring:**
  
  Continuously monitor the target directory for any changes in the files.
  Compare the current state of files against the saved baseline hashes.
  Alert the user if any file is added, modified, or deleted.
  Provide real-time notifications with color-coded messages for better visibility (e.g., green for new files, yellow for modified files, dark red for deleted files).
		
**Implementation Details**

  **Hashing Algorithm:** SHA-512 is used for its strong cryptographic properties.
		
  **Baseline Storage:** The baseline data is stored in a text file (baseline.txt) with each line containing the file path and its corresponding hash, separated by a pipe (|) character.
  Continuous Monitoring: The system uses a loop with a sleep interval of 1 second to continuously check for changes in the target directory.
		
**Usage Instructions**

		Collecting a New Baseline:
		Run the script.
		Select option "A" to collect a new baseline.
		The system will delete any existing baseline file and create a new one with the current hashes of the files in the target directory.
		
		Monitoring Files:
		Run the script.
		Select option "B" to start monitoring the files.
		The system will continuously check the target directory against the saved baseline and notify the user of any changes.
