At the start of the tutorial, you are given essentially the same water resource model you had at the end of tutorial 1, with all values in global variables 
"reservoir" and "flows". Files are as follows:

=> Matlab file "main.m" is the main script. Type "main" in the Matlab console to run everything.
It builds on the last version of "main.m" from tutorial 1 (with intake heights for demands) and adds a part where we'll compute performance indicators.

=> A new Matlab file, "preparation.m", takes care of extracting data from the Excel file into global variables "reservoir" and "flows". 
It gathers the parts of "main.m" that did that in tutorial 1 and does these operations in a single, separate bit of code.

=> Matlab file "water_balance_sop.m" is the final version of the water balance from tutorial 1, "water_balance_final.m". 
Its name comes from the fact that we use the Standard Operating Policy (SOP) to allocate water and determine the water balance.

=> Matlab file "water_balance_keep.m" is the same as "water_balance_sop.m" but with different order of priority for water users.

=> Matlab file "rrv_indicators.m" computes the indicators R (reliability), R (resilience) and V (vulnerability). 
It expresses V as the average of the (maximal) magnitude of failure during failure events, but has two versions: 1) V as the average distance to the threshold, 
and 2) V as the average percentage violation.

=> Matlab file "indicators.mat" contains the results: all the failure indicators for the different uses.

Update by Mustafa Onen on 24-04-2023
water_balance_sop.m and water_balance_keep.m has been updated with the following change.

head(t) is now gets updated after the update of water availability (wa) in the for block where reservoir water level is compared with the inlet elevation of each abstraction to decide abstraction or not.