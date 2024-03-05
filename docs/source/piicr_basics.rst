Phase-Imagaing Ion-Cyclotron-Resonance (PI-ICR) Basics
###########

The PI-ICR technique is a precision mass spectrometry technique. It determines the cyclotron frequency by finding the phase difference between ion clusters of different accumulation times projected on a position-sensitive detector.

Measurement Technique
**********

* Determine the center spot 
   * Inject ions at the center of the trap
   * Reduce residual motion
   * Extract ions towards detector
* Determine magnetron spot
   * Inject ions at radius r (using Lorentz steerers)
   * Free revolution for time t_acc (accumulation time) 
   * Extract ions towards detector
* Determine reduced cyclotron spot
   * Inject ions at radius r (using Lorentz steerers)
   * Quadrupolar pulse (to ensure ion motion is entirely reduced cyclotron motion)
   * Free evolution for time t_acc (accumulation time)
   * Quadrupolar pulse to convert motion to magnetron motion (smearing effect if extract at reduced cyclotron)
   * Extract ions towards detector

This procedure will result in 3 spots or clusters: center, magnetron, and reduced cyclotron. Next, PhIAT determines the phase between the magnetron and reduced cyclotron spots. 
