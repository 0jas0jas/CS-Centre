---
title: "Hardware"
date: 2023-03-25T12:55:37+05:30
draft: false
tags: ["Hardware", "AS_Level"]
categories: ["Hardware"]
---


# Storage
## Primary storage
#### RAM
- Used to store information that is currently in use by the device, stores parts of the currently running applications
- Volative(Content gets removed after the device is turned off)
 ### SRAM
 - Uses __Flipflops__ to store information,
 - Do not have to be refreshed constantly
 - Faster data access times
 - Expensive to manufacture
 - Low capacity
 - Uses more power
 - Used in processor cache
  ### DRAM
 - Uses **Transistors and capacitors**  to store information
 - They need to be constantly refreshed
 - Higher memory capacity
 - slower access times as compared to SRAM
 - Used and Random access memory
 - Consume less power
 - Cheaper to manufacture

# ROM
Permananent primary storage devices, they are non-volatile and the contents are store within the ROM chips permanently. 
They are used to store important information that is required by the device when starting up such as the __ BIOS | Startup instruction | OS(Only for smaller devices such as Printer) | Firmware | Bootstrap | Bootloader | __
### PROM
  - Consist of a matrix of fuses
  - Inorder to write data onto a PROM chip the individual fuses need to be "burned", due to which the PROM can only be written to once. 
 
  ### EPROM
 - Consist of floating gate transistors and capacitors, they can be rewritten after deleting the contents using UV light shined through a quartz window. 
###  EEPROM
- Data can be written and re-written using electric current. 
 - Consist of a grid of rows and column. 
 - They use floating gate and control gate transistors to store data
 - 2 Transistors are present at each junction of the grid, floating gate and control gate. 
 - The floating gate's only link to the control gate is through the wordline, if this link is in place then that junction has a value of 1. 
-  This effectively produces non-volatile memory. 


### Secondary storage 
### _Hard Disk drive_
> - Stores data on platters that spin at very high speeds. 
> - The data is accessed by fast moving read write heads that can move very faste between the hard disk surface. They are positioned just above the surface of each disk using an arm. 
>  - The disk are made from glass or aluminum oxide, and are covered in magnetisable material (ferrous oxide).
> - The disks are divided into tracks and sectors. 
> - Data is stored on magnetic disks. 
 
### _Solid state drive_
>  - They have no moving parts
> - They do not rely on magnetic properties. 
> - Data is controlled by the movement of electrons within NOR and NAND chips. 
> - NOR__(Uses EEPROM)__ and NAND uses __Flash memory__
> - EEPROM allows R/W operations in bytes. 
> - Faster,Reliable,Lighter,Thinner,cooler,Expensive, Do not have to get to speed. 

 
 ### _Optical storage_
>- Data is stored on discs
>- Data is read from and written onto a disk using laser light. 
>- Data is stored on disks made from plastic that are coated in metal oxide or light sensitive organic dye. 
>- Data is stored on the disk surface over a single spiral that runs from the center of disk to the outwards part.
> - The spiral is divided onto tracks and data is encoded as a series of pits and bumps. 
>- When data has to be read from a disk, a laser right starts from the centre where the beam contacts the disc surface. 
> - The light gets reflected onto an opto-electronical device. 
>- The sequence of pits and bumps causes the patterns of light reflected back towards the opto-electronical device to change, these changes are recorded and then interpreted by the deivice to data bits.  

### Embedded systems
>- Process of installing microprocessors on device to enable short single tasks to be done efficiently. 
> __PROS__: Efficient, consume less power,reliable
> __CONS__: Wasteful, interface can be confusing, 


# Output devices
## Printers
### Inkjet
>  - They spray CMYK or RGB ink on different spots in different quantities on the paper to produce the desired image. 
>  - Consist of a nozzles that spray ink, stepper motor and belt and a paper feed
>  - They use 2 technologies
>  - Thermal Bubble: Resistors create localized areas of heat that cause the ink to evaporate and form a bubble expanding on the paper, the bubble gets attached to the paper and forms a vaccume causing more ink to be drawn from the ink reservoir. 
### Laser
> - Use a laser beam and a rotating mirror to draw the image/text to be printer as areas of positive charge. 
> - Negatively charged toner then sticks onto a rotating drum 
> - Positively charged paper is rolled over the drum, which causes the toner to stick to the paper. 
> - The charge ont the paper is removed and the paper passes through fusers that melt the ink onto the paper.   

### 3D Printers 
> -  Uses solid material(Plastic, polymers, resin) to build a 3d object layer by layer. 
> - A nozzle is used that pours the molten plastic onto a surface in desired quantities. 
> - This is know as fused deposition modelling
> - Binder 3d printer involves 2 passes, one where the layer is build using a dry powder, then a binding agent is used like a glue to harden the layer so the powder gets binded together. 

## Audio
### Speakers
> Use a copper wire wrapped around __iron core, plastic/paper cone, and a permenent magnet __to produce sound.
> - It converts electric signals into sound as vibrations in the air. 
> - When current flows through the copper wire, it becomes a temporary electromagnet. 
> - The polarity of the electromagnet can be changed by changing the direction of  electric current. 
> - The direction of electric current is determined by the audio signals. 
> - As the audio signals change, the direction of the electric change, this rapidly varies the polarity of the electromagnet. 
> - The change in polarity causes the copper coil to be attracted to or repel the permanent magnet. 
> - This causes the copper coil to vibrate. Since the copper coil is connected to the cone using a diphragm, the cone also vibrates and produces sound. 


 

## Screens
### OLED
#### Resistive_TouchScreens
> - Consist of an upper glass layer that has a resistive and a conductive layer, and a bottom layer. 
> - Current runs over both layers 
> - When the user presses the upper layer, it bends to make contact with the bottom layer. 
> - A circuit gets completed 
> - An onboard microprocessor determines the position of the touch by looking at changes in the electric field.
> __PROS: __ Inexpensive, allows a user wearning gloves
> __CONS:__ Screen visibility poor in sunlight, Easy to scratch, 

#### Capacitive_TouchScreens
> - Consists of 2 layers that act like capacitors creating charge in between. 
>  - When the user touches the screen, charge gets transferred from the screen to the user. 
> -  When this happens a microprocessor determines the position of touch by claculating the relative diferrence in the amount of charge at each corner of the screen.
> __PROS:__ Medium cost, durable, visibile under sunlight
>  __CONS:__ Input not detected if wearing glove

