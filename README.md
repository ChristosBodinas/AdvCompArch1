### Ερώτημα 1

Για το πρόγραμμα hello, χρησιμοποιήθηκε ο MinorCPU, ο οποίος διαθέτει ξεχωριστά level 1 cache για δεδομένα (L1D) και εντολές (L1Ι), ενιαίο level 2 cache και walk cache.  
Για την αλλαγή της συχνότητας του επεξεργαστή, μπορούμε να προσθέσουμε στην εντολή το argument  
--cpu-freq='CPU_FREQ'.

### Ερώτημα 2

Από το αρχείο code/hello_result/stats.text:

*	sim\_seconds			0.000035		# Number of seconds simulated  
*	sim\_insts			5027			# Number of instructions simulated  
*	host\_inst\_rate		67875			# Simulator instruction rate (inst/s)


### Ερώτημα 4a

Έτρεξα ένα απλό πρόγραμμα C (squares.c) που εκτυπώνει τα τετράγωνα όλων των ακεραίων από το 1 έως το 1000, χρησιμοποιόντας πρώτα το MinorCPU και μετά το TimingSimpleCPU.

Για το MinorCPU, έχουμε από το αρχείο results\squares\_minor\stats.text:

*	sim\_seconds			0.000518		# Number of seconds simulated  
*	sim\_insts			662115			# Number of instructions simulated  
*	host\_inst\_rate		311644			# Simulator instruction rate (inst/s)

Για το TimingSimpleCPU, έχουμε από το αρχείο results\squares\_timingsimple\stats.text:

*	sim\_seconds			0.001030		# Number of seconds simulated  
*	sim\_insts			659549			# Number of instructions simulated  
*	host\_inst\_rate		894713			# Simulator instruction rate (inst/s)

Βλέπουμε λοιπόν ότι ο MinorCPU εκτελεί το πρόγραμμα πιο γρήγορα από τον TimingSimpleCPU.


### Ερώτημα 4b

Τρέχοντας το ίδιο πρόγραμμα με τους ίδιους επεξεργαστές, με διάφορα είδη μνήμης DDR3 και DDR4, δεν παρατηρούμε σημαντική αλλαγή στις επιδόσεις κανενός από τους δύο επεξεργαστές. (results\squares\_minor\_freq\_x και results\squares\_timingsimple\_freq\_x)

Τρέχοντας το πρόγραμμα για διαφορετικές συχνότητες (από 1GHz έως 2.5GHz), παρατηρούμε ότι και η δύο επεξεργαστές έχουν μεγάλη ευασθησία σε αλλαγές της συχνότητας.
