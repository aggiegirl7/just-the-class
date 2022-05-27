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

* **Active attacks**
     - i/ps and operating environments are manipulated (tampered device)
     - device is operated abnormally
     - exploit the secret key to detect abnormal behavior

**Another classification is based on the interface (logic + physical)**  
  
**Some of them can be accessed easily or need special equipment**

* **Invasive Attack**
     - practically no limit on what you can do (can be destructive)
     - typically depackage the device, access the devoce through a probe station, laser cutters
     - *very powerful!*  

* **Semi-Invasive Attack**
     - may involve depackaging, but no electrical contact
     - typically used to read-out memory contents of the device without probing
     - goal is to induce faults using x-rays, electromagnetic fields, light, sound (!) 
     - may not need expensive equipment
     - but relatively more effort than invasive because finding the right location to attack takes effort 

* **Non-Invasive Attacks**
     - only directly accessible interfaces are touched
     - no permanent alteration to the device -> no evidence of an attack
     - requires relatively inexpensive equipment
     - three major classes  
          1. Power (This class!)
          2. Timing
          3. EM

## Power Analysis Attacks 
     - started in 1999 (check out Kocher's famous paper)
     - one of the most famous attacks
     - companies have specific positions
     
 *Power analysis attacks exploits the fact that instantaenous power depends upon the data being processed and operation being performed*
 
 ![Book logo](/assets/images/power1.png)
 
 - μc is executing AES (software version)
 - encrypts plaintext from PC and send back the ciphertext
 - 1 Ω resistor to measure the current (through the voltage drop)
 
  ![Book logo](/assets/images/power2.png)
  
  - First .35 ms, quite uniform  
              -> μc is waiting for plaintext  
  - After getting plaintest 9 fullround AES is performed  
               -> each round is approximately .4 ms  
               -> notice the negative peak  
   - 10 round is shortened
   - 4.1 ms powertrace becomes uniform 
         
          
