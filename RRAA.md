#Robust Rate Adaptation for 802.11 Wireless Network 
http://ocw.cs.pub.ro/courses/_media/isrm/articole/rrate_adapt_mobicom06.pdf

###1.Contributions (What are the major issues addressed in the paper? 
Exploit flaws in the design guidelines suggested for the 802.11 rate adaptation. 
Suggest and evaluates algorithm on the basis of the improved design guidelines. 

###2.Do you consider them important? Comment on the novelty, creativity, and technical depth of the paper.)
Yes, they are important as the author performed various experiments to prove their methodology.
It uses adaptive RTS filter and frame loss ratio to calculate rate adaptation.

###3.Briefly summarize the main ideas/the approach to the solution.
Expose flaws in the design guidelines used in rate adaptation for wireless network.
They focus on 
* the hidden terminal issue 
* incorrect rate estimation due to probe packet
* SNR
* large sampling period
They also present enough experimentation proof for the above mentioned issues.
They propose solution for rate adaptation by calculating frame loss ratio 
within short period of time and suppressing the hidden terminal problem using Adaptive RTS Filter.

###4.What are the paper's strengths? Be brief.
Paper presents the algorithm for rate adaptation by focusing on the flaws of the existing guidelines for rate adaptation in 802.11. 
Also it compares its experimental result with the existing algorithms like ARF, AARF, Sample Rate.

###5.What are the paper's weaknesses? Be brief.
It address 3 practical issues like 
* ideal condition, 
* multiple active station 
* variable packet size 
and also solution but they did not evaluate their result with the experiments.

###6.Comment on the paper's evaluation methodology.
Results are evaluated using 
 * programmable AP with static/mobile clients, 
 * with/without hidden channel, 
 * Using the 802.11a/b channel, 
 * With TCP/UDP traffic in ideal/uncontrolled conditions.

###7.Are there any issues/directions this work left open? List a few possible extensions of this work.
* Author critics on 5 design guidelines for 802.11 a/b/g, 
 are these critics also hold same for the MIMO ?
* Can we use the same algorithm for the MIMO ?
* Can we generalize this algorithm to use for the MIMO / Can we use the conclusions from this paper in MIMO?
* Can we compute energy consumption for the given protocol (RRAA)?
* Can we use this algorithm in the overlapping channel?

###8.Any other comments/questions.
* When A-RTS exceeds threshold they disable threshold then ,
* how they toggle between rate adaptation and fixed rate(i.e. are they using TO mechanism or RTS is still enabled)?
* This RA scheme uses feedback from physical layer is this scheme implemented in sender or receiver or in both?
* If it uses feedback mechanism then is that mechanism introduces any delays or overhead?
