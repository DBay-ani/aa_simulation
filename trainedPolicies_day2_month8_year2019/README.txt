This folder containes trained policies meant to be shared with Aman Khurna on day2 month8 year2019.
The tarred-and-compressed file experimentsUsingCPOConstraintsInTrainingWithoutUsingCPO.tar.gz contains
the trained policies in question, formed using:
   <root of git repo>/train/train_monitorEncorporated_circle_planner.py  
   <root of git repo>/train/train_monitorEncorporated_straight_planner.py
Due to some incidents training, some policies were trained using the same variant multiple times. In
order to see what policies were trained using what variant, use the following terminal command in the
folder housing all the policies from experimentsUsingCPOConstraintsInTrainingWithoutUsingCPO.tar.gz:
    for thisFile in $(find . | grep variant.json); do echo -n $thisFile "1234567890098765432112345678900987654321";  cat $thisFile | grep "\(dt\)\|\(eps\)\|\(radius\)\|\(seed\)\|\(target_velocity\)\|\(useQuantMonitorSubformulasAsFeatures\)\|\(weightForQuantMonitorValueInReward\)\|\(codeForFallbackController\)\|\(quantitativeMonitorSubFormulas\)" | sort | awk   'BEGIN{ORS=" "}{print $0}'; echo ""; done > temp

It will fill a file called temp with content of form:
    <file name><delimitor><variant information>
where <delimitor> is the string 1234567890098765432112345678900987654321 .
