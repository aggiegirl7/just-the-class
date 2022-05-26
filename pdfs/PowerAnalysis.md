# Power Analysis 

*The following notes are from the book "Power Analysis" by Stefan Mangard*

## Smart Cards
* most popular kind of cryptographic devices 
* most of them are equipped with a microcontroller
* In 2003 - 1 billion smart cards  
     2006 - 2 billion  
     2018 - ?  
     
 #### Most of them are used in security- sensitive applications such as...
 * Telecommunications
 * Financial Services
 * Government Services
 * Pay TV
 * IoT (Internet of Things) ?

**They are usually eqipped with software or hardware performing cryptographic algorithms**
* A common feature in RFID and USB tokens 

## Some Thoughts
* Crypto devices are hardware that store keys and perfom crypto operations  
* Security of system security of cyrpto algorithm  
  - one needs to consider the security of crypto devices 
* Attackers are going to steal the key in an unauthorized way.
* Security of a crypto device should not reply on the secrecy of the implementation  
-> *Security through obscurity*

## Attacks on cyrpto devices- categorization 
* **Passive attacks**
   - operated largely or entirely within the specification
   - secret key is revealed by observing physical properties (eg. power consumption, timing)
