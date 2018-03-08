## Transfering files to QUEST

1. Transfer files from sequencing facility server directly to QUEST using your favorite file transfer tool. Transmit and Cyberduck are good options for macOS.

    **NOTE:** New sequence data should be stored in the appropriate path on the cluster in the `raw` directory. For example, when adding new sequence data for wild isolates, data should be added to a new folder here:
    `/projects/b1059/data/fastq/WI/dna/raw/<folder_name>`

2. Rename files using proper file naming convention. 
    
    `<strain name>_<sequencing facility file name>_1.fq.gz`
    OR
    `<strain name>_<sequencing facility file name>_2.fq.gz`

    **NOTE:** If sample names are not present in the fastq file from the sequencing facility they can be added with a rename script. Generate a rename script `rename_<your project>.sh` using the following convention. 
    ```
    #!/usr/bin/env bash
    mv <old file name for strain a> <new file name for strain a>
    mv <old file name for strain b> <new file name for strain b>
    ```
    You can create this script quickly using googlesheets. Use the sequencing sample submission sheet in Dropbox as a lookup table. The `VLOOKUP` function can match `strain name` with the `sequencing facility sample name`. Use the `CONCATENATE` function to create a column containing commands for the rename script. Copy that column into a text editor and save as .sh script file. Run the script on the directory containing your files using `bash <your rename script>.sh` 

3. Update 


