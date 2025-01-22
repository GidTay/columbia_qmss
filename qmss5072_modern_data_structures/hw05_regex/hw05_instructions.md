# QMSS G5072 Homework 5
# Working with Strings: Analyzing NTSB Aviation Incident Narratives
## Thomas Brambor 

## Context

We’re exploring a dataset containing narratives from ~6k aviation incident reports from 2021 to 2024 from the National Transportation Safety Board (NTSB) Aviation Incident Database. Your goal is to extract structured information from unstructured text data using regular expressions and perform basic analysis of aviation incidents.

## Dataset Overview

The dataset `ntsb_narratives_2021_2024.csv` contains textual descriptions of aviation incidents. The narratives may contain details like aircraft models, pilot experience, airport codes, and engine failures. For example:

```text
On September 11, 2024, about 0940 mountain daylight time, a Cessna 172S airplane, N20747, was substantially damaged when it was involved in an accident near Meridian, Colorado. The pilots sustained minor injuries. The flight operated under the provisions of Title 14 Code of Federal Regulations Part 91 as an instructional flight.

The airplane was performing touch and go landings to runway 17R at the Centennial Airport, Englewood, Colorado. When on climb out for the traffic pattern, the airplane was about 200 ft above ground level when the pilots noticed a partial loss of engine power. The instructor reported the engine RPMs to read 2,100 and then 1,600. He performed a forced landing to a golf course and during the landing roll, the airplane's nose landing gear collapsed, and airplane came to rest inverted.

The airplane was retained for further examination.
```

## Exercise

### 1. Engine Incidents and Failures

#### a) Extracting Engine Incidents

Find narratives mentioning the word “engine” (or "engines"). Create a boolean column engine (called `engine`) that marks incidents as engine-related or not. Show the count of engine-related narratives.

_Note_: To simplify, there is no need to consider alternative terms like “Powerplant, Motor, Turbine, Propeller, Jet.” We'll just focus on `engine` but do account for plural/singular and capitalization.

#### b) Use regular expressions to specifically extract narratives that describe engine failures, differentiating them from general engine incidents.

Create regex patterns to capture terms like `engine failure`, `engine stopped`, or `failed engine`. Consider the two (2) words before or after the term “engine” (or its variations) to identify narratives describing failure.

_Note_: No need to go overboard to be fully comprehensive but do show your abilities to employ the following regular expression techniques: 
- finding alternatives
- handling optional words
- identify word boundaries
- account for singular/plural and capitalization

Create a boolean column called `engine_failure` that marks engine related incidents as engine failures or not.

Provide summary statistics of what proportion of the narratives in the dataset contain a mention of the engine, and what proportion of these mentions you identified as engine failures.

#### c) Randomly select 10 entries from the dataset. Display the portion of the narratives with the 2 words before and after the mention of engine, alongside your two new variables `engine` and `engine_failure`. Briefly discuss how this identification process could be improved. Mention potential issues with false positives or missed entries.

### 2. Extracting the Time of Day

#### a) Use regular expressions to extract the time of day from the narratives. Look for patterns such as:
  - "0940"
  - "14:30"
  - "2:15 PM"
  
- Your regex should be able to identify various time formats including:
  - **24-hour format** (e.g., 0940, 14:30)
  - **12-hour format** with AM/PM (e.g., 2:15 PM, 11:00 AM)
  
- Extract the time and create a new column `time_of_day` that stores the time in a uniform format (e.g., 24-hour format). If no time is mentioned in the narrative, leave the field blank.

_Hints_:
- Use capturing groups in your regex to extract the hours and minutes.
- For 12-hour formats, ensure that you correctly convert the time to 24-hour format (e.g., 2:15 PM should become 14:15).  

Show the first 5 entries where the time_of_day is successfully extracted.
Provide a summary statistic on how many of the narratives contain a time mention.

#### b) Analyze the relationship between time of day and engine failures. Create a bar plot where the x-axis represents the hour of day and the y-axis represents the proportion of engine failures (as a share of all mentions of the aircraft model). Comment briefly on what you found.

### 3. Identifying Aircraft Models for a Common Manufacturer

##### a) Use regular expressions to search for mentions of the following 10 manufacturers in _all_ incidents: `Cessna, Piper, Beechcraft, Boeing, Airbus, Cirrus, Robinson, Embraer, Bombardier, Mooney`. Count how many times each manufacturer is mentioned and show the information in a table, alongside the share of engine failures.

_Hint_: To simplify, there is no need to account for misspellings or abbreviations of manufacturer names.

#### b) For the single most common aircraft manufacturer identified in (3a) only, create a regular expression to extract aircraft models related to that manufacturer. For example, for Cessna, you might expect models like “Cessna 172”, “Cessna 182”, “Cessna 150” (but do account for variations like “Cessna 172”, “Cessna-172”, “172 Cessna”), for Piper the models may be of the format "Piper PA-28, Piper PA-32". 

Count how many times each model is mentioned in the dataset for the manufacturer and create a table showing the model number, number of mentions, share of engine related incidents, and share of engine failures. 

Note: Throughout the assignment, ensure that you handle variations in wording, capitalization, and abbreviations. Use regular expressions efficiently to capture as many relevant cases as possible. Comment your code to explain your logic and any assumptions made.

## Submit your homework

Please follow the [instructions](/Exercises/homework_submission_instructions.md) to submit your homework. The homework is due on Wednesday, October 16 at 5pm.
