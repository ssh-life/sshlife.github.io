title: SecureBoot
date: November 10, 2021
author: switch

This post talks about what secure boot is from a very high level. Secure boot is a simple concept, but like many things with security a simple concept becomes very difficult due to the small but impactful details in computers we have today.

#Vocabulary
Went back and forth a lot about whether or not to use certain terminologies to avoid overloading the reader but it's important to keep things accurate and hopefully this section will gently introduce some of the terminologies.

SoC - System-on-Chip. This is your CPU, it's almost a small machine in itself and has it's own dedicated memory and peripherals that other components on your device cannot access.


#What is Secure Boot
Secure boot protects the integrity of your software. Meaning when your device is booting up, it is ensuring that the software running on your hardware has not been tampered with by a "hacker". Many of you may have heard the term "locked bootloader" and unfortunately there's quite a bit of negative connotation with term. But the reason many device manufacturers lock their bootloader is to protect the software running on the device so that customers can trust their own devices.

#How Devices Boot
Diagram below shows a very abstract boot chain and we're leaving out a lot of details to avoid overwhelming anybody. Promise there'll be a follow up where we go into a lot more detail and talk about the secure bot in ARM with the TF-A/TF-M boot process.


1. bootROM - The first set of instructions that your device will run after it powers on. This is your source of truth and everything else anchors on the trust of your bootROM. The secure boot process is a sequential chain of trust, whatever the story is starting from the bootROM, everybody else in the chain will tell the same story.
2. BootloaderX - Before your operating system is up and running and you can play your favorite game on your phone, there's a lot of hardware that needs to be initialized and the memory on your System-on-Chip (SoC).
