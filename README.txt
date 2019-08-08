****************
RegulomeDBScraper.py
****************************
Authorship:
Bilal Moiz (with input from rbierman of http://stackoverflow.com/questions/40539237/using-requests-to-navigate-through-multiple-pages)
11/15/2016


Description:

This script is designed to analyze large sets of variants by subjecting them to interpretation via
RegulomeDB, which is unable to handle such massive sets on its own. It appears to only take in about
1000/session. This script will open a new file (regulome_IDs.txt), then open the input file. It 
loops through the input file and appends each line into a list of strings called "lines". Once there
are 101 variants in each chunk, it submits them to regulomeDB using the requests module. This will
return the text contents of a 'bed' file (chosen for its simplicity to parse). These 'bed' contents
are then appended to 'File_compiler". Once this has been completed, the script will then loop
through each chunk in file compiler and using regex, write them in the correct format to our output file.

This specific script has been designed for ZeroCoords input, although support for other forms 
can be added in the future. 


**************
How to run 
**************

This script requires the usage of the Requests package, which supports Python 2.7, but will need to be installed on our linux machines.
To run it,  navigate to the folder containing the script using cmd. 

Run the following command:

python RegulomeDBScraper.py --I (put location of your input file here) --O (output file name here) 


For now, make sure your input is in 0-based coordinate format. I am planning to add support for other formats in the future.

************
Other Notes
************

I have included two sample inputs ("ExampleInput_chr6SNP.txt" and "ShortInputExample.txt"). I have also
included a sample output (which annotated the variants included in the "ExampleInput_chr6SNP.txt" file)
so that you can see what your output should look like.