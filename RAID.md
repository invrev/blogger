A case study for Redundant Arrays of Inexpensive Disk (RAID)  
http://www.eecs.berkeley.edu/Pubs/TechRpts/1987/CSD-87-391.pdf  

* Performance of the system increased with improvement in the performance of 
1.CPU   
2.Memory  
3.I/O  

* I/O system is evaluated based on the following attributes    
###1.Performance    
    At abstract level 2 types of systems need to be considered to measure the performance    
    1.TPS (Random access)    
        Read,Write and modify (Search)    
    2.SuperComputer applications (Sequential access)    
        Read and write   
###2.Power consumption  
###3.Scalability  
###4.Cost   
###5.Reliability  
    * Achieved by increasing the MTTF  
    * However,the curse of the scalability  
    * MTTF = MTTF of single disk/ # of disk  
    * Ultimately if we increase the # of disks MTTF reduces  
    * Idea : Use of MTTR   
    * look at the bigger picture  
    * reduction in the MTTR result into increase in the MTTF.  
    * MTTF = (MTTF / G+C) * 1/prob. of another failure  
    * prob. of another failure = MTTR / (MTTF / # of disks - 1)  
    * Next prob of failure = MTTR / (MTTF / # of remaining disks - 1)  
  
###RAID types
####Types of disks used   
*  Data disk  =  G  
*  Check disk/parity disk  =  C  
*  RAID0 (JBOD  =  Just Bunch of Disk) C = 0  
*  RAID1  =  Mirrored Disk (G=C= 1)  
   Double the storage cost/Use only 50% of the storage space  
*  RAID2  =  Hamming code for error correction  
   Error correction requires more disk than error detection  
   A parity disk can detect the single error  
*  RAID3  =  Single check disk/Parity disk per group  
*  RAID4  =  Indepnedent reads and writes  
*  RAID5  =  Spread data * parity over all disks (no single check disk)  

###RAID can be implemented as application using logical sectors and disk  
https://raid.wiki.kernel.org/index.php/RAID_setup#Linear_mode  

###Used terms and notations
* MTTF = Mean Time To Fail  
* MTTR = Mean Time To Repair  
