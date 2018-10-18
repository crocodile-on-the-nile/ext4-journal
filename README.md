# ext4-journal
A script to parse the contents of ext4 journal

Provide executable permissions to the script before running it

$ sudo chmod +x parse_journal


Run script as 
$ sudo ./parse_journal file_system_image.dd

By default, only information about the first 64 journal blocks are displayed - from block 0 to block 63.

To view information about all the blocks, in line 75, modify the condition part of the for loop as

block<=$(($j_nblocks-1))

where j_nblocks is the total number of blocks in the journal. Since block numbering starts from 0, we have decremented 1 in the condition.

