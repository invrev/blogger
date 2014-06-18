#Intersection of a number theory and an algorithm  
  
I personally view an algorithm is an art while   
number theory (Arithmetic from the Greek view)is branch of the mathematics.  
The RSA ,a lot of information is available on the internet.  
  
###Used Notations are  
Private/secret variables at the receiver side  
* p,q = Randomly selected prime numbers  
* k’ = Private key/exponent  
* ƒ(p,q,n,k)—»k’ = Function that derives the private key  
* Private/secret variables at the sender side  
* m = Message to be sent  
Public/open to all variables  
* c = Encrypted message    
* n = Public key/modulus    
* k = Public key/exponent  
  
###Some of the decisions in the RSA are    
####1.Use of the prime numbers  
* According to the Euclid’s proof, there are infinitely many primes.  
* This helps us to select the prime numbers from the infinite sample space.   
* To compute the public key we select 2 random prime numbers and then we multiply them.   
* Though,each natural number is represented by product of unique sequence of prime numbers   
either increasing or decreasing order ,it’s computationally very hard to   
backtrack the randomly selected prime numbers   
given the public key with caveat that we have a very large public key.  
* This also concludes that prime numbers are the basic nucleus/atoms of the natural numbers.  
  
####2.Use of 2 public keys                                                                  
* It uses 2 public keys with notation k,n. n act as modulus while k acts as public exponent.  
* The naive reason is to decrease the probability of finding the secret key k’.  
  
####3.Use of the mod operator  
* In RSA,we use mod operator during message encryption and decryption at a client (peer/sender) side or at a server (peer/receiver) side respectively.  
* RSA,selected to use the mod on the basis of it’s mathematical property.  
* I did not find any convinced reason about this.  
* During the process of encryption we know m,n,k so we can encrypt m to c  
* c = m^k (mod n)  
* This process will be computationally expensive is use naive approach of computing m^k and then  
* perform mod n.One thing to notice is that c<n so the n is upper bound.  
* To compute “c” efficiently we can use modular exponentiation (log n) or Chinese remainder theorem.  
* And at receiver side we decrypt the message as  
* m = c^k’(mod n)  
* If we don’t know the k’ then to compute the k’ is computationally expensive.  
  
####Reference  
* A Method for Obtaining Digital Signatures and Public-Key Cryptosystems  
 http://people.csail.mit.edu/rivest/Rsapaper.pdf  
