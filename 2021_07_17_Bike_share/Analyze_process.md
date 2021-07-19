Hi,

Ready first the case study to be sure that we start from the same point. The link for the file used can be found there. I use the dataset from **2020-04** to **2021-06**.

Explanation of the analyze process :


1. **Load and merge dataset**

   This part is not the most complicated one. Just some knowledge in Python is enough.
   I just write all the files name in a list and store it in a variable. Then i combine `Pandas` and `Loop` to put everything in one file. Then again, store it in a variable (called `df` for me).
2. **Cleaning**

   The first is the most mandatory and important one. Bad input results in bad output.
   Before starting, make a copy of the dataset, do not work with the initial dataset variable. We never know if we need the original dataset afterward (i will work with a dataset stored in `df1` variable.
   
   1. **NaN values**

      `NaN` values break the analyze. It is sometimes a real pain to know what to do with them. Two options :
      - [X] Delete them (`dropna` in `Pandas`)
      - [X] Complete them (using `svd`)
      
      In my case, i drop them because i have more than 4M rows of data.
   3. **data formatting**
      
      Convert your data to the correct type (`number` to `int` format for example).
   
   2. **Check for errors**

      I decide to have a look to all uniques values of each column. I then correct some spelling mistakes.
   
   3. **Delete useless columns or combine them**

      What is useless should be decided case by case. Some examples :
      - [X] Unique value column
      - [X] Redundant details (like `adress` and `id`)

      In my case, i decide to delete `started_at` and `ended_at` but i create a new column called `time` which is just `ended_at - started_at`. Much simpler for later analysis.

