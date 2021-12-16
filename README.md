### Ερώτημα 1

Για το πρόγραμμα hello, χρησιμοποιήθηκε ο MinorCPU, ο οποίος διαθέτει ξεχωριστά level 1 cache για δεδομένα (L1D) και εντολές (L1Ι), ενιαίο level 2 cache και walk cache.  

Χρησιμοποιεί μνήμη 2GB DDR3_1600_8x8 και τρέχει με συχνότητα 1GHz, την οποία μπορούμε να αλλάξουμε προσθέτοντας το argument --cpu-freq="CPU_FREQ".

### Ερώτημα 2

Από το αρχείο code/hello_result/stats.text:

*	sim\_seconds			0.000035		# Number of seconds simulated  
*	sim\_insts			5027			# Number of instructions simulated  
*	host\_inst\_rate		67875			# Simulator instruction rate (inst/s)


### Ερώτημα 3

IL1.miss_num = system.cpu_cluster.cpus.icache.demand_misses::.cpu_cluster.cpus.inst = 327  
DL1.miss_num = system.cpu_cluster.cpus.dcache.overall_misses::.cpu_cluster.cpus.data = 177  
L2.miss_num = system.cpu_cluster.l2.overall_misses::total = 474  
Total_inst_num = sim_insts = 5027  
CPI = 6.3160931


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

MinorCPU με σταθερή μνήμη, αλλά διαφορετικές συχνότητες:  
1.0GHz    0.000922 secs 
1.5GHz    0.000656 secs 
2.0GHz    0.000518 secs 
2.5GHz    0.000438 secs

TimingSimpleCPU με σταθερή μνήμη, αλλά διαφορετικές συχνότητες:  
1.0GHz    0.002027 secs 
1.5GHz    0.001364 secs 
2.0GHz    0.001030 secs 
2.5GHz    0.000831 secs

MinorCPU με σταθερή συχνότητα, αλλά διαφορετικά είδη μνήμης:
DDR3_2133_8x8     0.000516 secs 
DDR4_2400_8x8     0.000517 secs 
DDR3_1600_8x8     0.000518 secs 
DDR4_2400_4x16    0.000518 secs 
DDR4_2400_16x4    0.000517 secs

TimingSimpleCPU με σταθερή συχνότητα, αλλά διαφορετικά είδη μνήμης:
DDR3_2133_8x8     0.001029 secs 
DDR4_2400_8x8     0.001030 secs 
DDR3_1600_8x8     0.001030 secs 
DDR4_2400_4x16    0.001032 secs 
DDR4_2400_16x4    0.001030 secs

Βλέπουμε ότι και οι δύο επεξεργαστές αντιδρούν ελάχιστα στην αλλαγή του είδους μνήμης, αλλα επηρεάζονται πολύ περισσότερο από μεταβολές στη συχνότητα τους.


Τρέχοντας το πρόγραμμα για διαφορετικές συχνότητες (από 1GHz έως 2.5GHz), παρατηρούμε ότι και η δύο επεξεργαστές έχουν μεγάλη ευασθησία σε αλλαγές της συχνότητας.
