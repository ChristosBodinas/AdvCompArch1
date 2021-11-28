### Ερώτημα 1

> **Βασικές παράμετροι που έχει περάσει στον gem5 για το σύστημα προς εξομοίωση; Καταγράψτε τα βασικά χαρακτηριστικά του συστήματος, όπως ο τύπος CPU, συχνότητα λειτουργίας, βασικές μονάδες, caches, μνήμη, κτλ. Πώς θα μπορούσατε να αλλάξετε τη συχνότητ λειτουργίας του συστήματος;**


### Ερώτημα 2

Από το αρχείο hello_result/stats.text:

*	sim\_seconds			0.000035		# Number of seconds simulated  
*	sim\_insts			5027			# Number of instructions simulated  
*	host\_inst\_rate		67875			# Simulator instruction rate (inst/s)


### Ερώτημα 3

> **config.ini και config.json... Υπολογίστε το CPI με βάση τα αρχεία αυτά**


### Ερώτημα 4

> **gem5.org αναζητήστε πληροφορίς για τα διαφορετικά μοντέλα in-order CPUs που χρησιμοποιεί ο gem5 και παραθέστε μια συνοπτική παράγραφο για καθένα από αυτά**


### Ερώτημα 4a

Έτρεξα ένα απλό πρόγραμμα C (squares.c) που εκτυπώνει τα τετράγωνα όλων των ακεραίων από το 1 έως το 100, χρησιμοποιόντας πρώτα το MinorCPU και μετά το TimingSimpleCPU.

Για το MinorCPU, έχουμε από το αρχείο squares\_result\_MinorCPU\stats.text:

*	sim\_seconds			0.000081		# Number of seconds simulated  
*	sim\_insts			70234			# Number of instructions simulated  
*	host\_inst\_rate		283366			# Simulator instruction rate (inst/s)

Για το TimingSimpleCPU, έχουμε από το αρχείο squares\_result\_TimingSimpleCPU\stats.text:

*	sim\_seconds			0.000133		# Number of seconds simulated  
*	sim\_insts			69934			# Number of instructions simulated  
*	host\_inst\_rate		283366			# Simulator instruction rate (inst/s)

Βλέπουμε λοιπόν ότι ο MinorCPU εκτελεί το πρόγραμμα πιο γρήγορα από τον TimingSimpleCPU.


### Ερώτημα 4b


