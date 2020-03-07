# Check50 for Heuristics
**Author:** Okke van Eck  
**Check50 Docs:** https://cs50.readthedocs.io/check50/  
**Note:** All `test.py` files are gitignored!  

#### Setup check environment.
You must have python3 installed and a possibility for creating a virtual
environment. The example below uses the python3-venv package, but you can use
your own as well.

###### Install packages.
`sudo apt-get install python3 python3-venv`

###### Create virtual environment and activate it.
```shell script
python3 -m venv venv
source venv/bin/activate
```

###### Install requirements.
`pip install -r requirements.txt`


#### Run checks.
It is possible to run the check50 tests via the online version on GitHub, or
locally in a development environment. The different options are separated in 
sections. For all checks, you must be in the folder of the check itself. So
`cd` into the directory of the case you want to test. Let's
denote the folder name of the case as `<case>`.    

###### Run on the check50 servers.
You can run the checks on GitHub on the check50-servers by running the command:  
`check50 OkkeVanEck/cs50_heuristieken/master/<case>`

###### Run locally
You can run the checks on GitHub locally by running the same command with the
`--local` flag specified:  
`check50 --local OkkeVanEck/cs50_heuristieken/master/<case>`

###### Run local code
You can run your local version of a check by running `check50` with the 
`--dev` flag in the folder where the `.check50.yaml` is located:  
`check50 --dev .`


### Required case changes
There are some changes required for the cases. The changes are de described 
below, devided by case. For each case it will be necessary to write an 
explanation on how to use the check50.

##### Protein Powder
- Remove spaces behind comma's in `example_output.csv`
- Add a footer to output.csv with the score: `score,<integer>`

##### AmstelHaege
- Remove spaces behind comma's in `example_output.csv`
- Ask for all four corners in order instead of two
    - Rename header to `structure,corner_1,corner_2,corner_3,corner_4,type`
- Add a footer to output.csv with the networth: `networth,<integer>`
- Change the project info to only except a map dimension of 180x160 where 180 is the width.
- Change the given neighbourhood files and `example_output.csv` to have the 180x160 dimension instead of 160x180.

##### RailNL
- Edit `Noord-Holland` in part one into `Noord- en Zuid-Holland`
- Change `ConnectiesHolland.csv` distances into floats
- Make the following changes to `example_output.csv`:
    - Remove spaces behind comma's
    - Change header to `train,stations,problem`
    - Add footer with `score,<integer>,<problem>` where problem is either `NL`
        or `NZH`, representing the corresponding problem
    - Change `Amsterdam Amster` into `Amsterdam Sloterdijk`
    - Change `Goude` into `Gouda`
- Change filenames to English in every file
- Create `StationsHolland.csv` file in the same way as `StatinosNational.csv`
- Add header `station,x,y` to `StationsNational.csv` and `StationsHolland.csv` 
- Add header `station1,station2,distance` to `ConnectionsHolland.csv` and 
    `ConnectionsNational.csv`
- Make ints from the floats in `ConnectionsNational.csv` or vice versa in `ConnectionsHolland.csv`