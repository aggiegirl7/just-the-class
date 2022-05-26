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
