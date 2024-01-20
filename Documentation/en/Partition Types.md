# Partition Types

◦ **Primary:** The only partition where an operating system can be installed. There can only be 4 primary partitions per hard disk or 3 primaries and one extended.

◦ **Secondary/Extended:** Designed to break the limitation of 4 primary partitions on a single physical disk. There can only be one partition of this type per disk, and it serves only to contain logical partitions.

◦ **Logical:** Occupies a portion of the extended/primary partition or its entirety, which has been formatted with a specific type of file system (in our case, we will use ext4) and assigned a unit so that the operating system recognizes logical partitions or their file system. There can be a maximum of 23 logical partitions in an extended partition; however, Linux, the current operating system we are working with, reduces it to 15, more than sufficient for this project.