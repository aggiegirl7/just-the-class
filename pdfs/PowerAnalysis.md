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

![power3](https://user-images.githubusercontent.com/92998559/170603351-d3e03b7b-2a83-47c3-aa34-b501982f5cbb.png)

 Power consumption (zoomed view)
 
 - Power trace in 6 clock cycles
 - Each peak -> 1 clock cycle
 - Peaks are different  
          -> depends on operation  
          -> depends on data  
          
  **Simple Power Analysis (SPA)**  
  -> one powertrace is good enough to leak the secret 
  
 
![power4](https://user-images.githubusercontent.com/92998559/170603627-8e49a9e6-975a-41fd-908c-a02bbb2b34e9.png)

- Peaks reveal the moments of time  
                              -> depends on the data   
                              -> depends on the operation  
- Highest peak is at 132 μs  
          -> this is when the byte containing the MSB is loaded  
- Power for d = 0 and d = 1 are almost the same except for 3 clock cycles  
                              -> That's the moment of interest  
                              -> This is whe d or data related to d is processed  
    *Can we exploit this? -> power analysis*   
    
    **Example with key:**
    - Plaintext (p) is first XORed with roundkey (RO); let's say Ro = k  
    - Substitution box is then performed  
    - Power consumption at some point  
     
    ![power5](https://user-images.githubusercontent.com/92998559/170604280-39b643c1-e278-43f8-83b4-a3c7a50991ab.png)


          
