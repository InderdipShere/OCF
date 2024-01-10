# OCF
Orientation Correlation function
Program file: OCF.f90
! calculates Orientiation Correlation function (OCF) from the trajectory file for a single molecule.
The atom A and atom B is used for construting direction vector. The orientation of this direction vector is monitored throughtout the trajector and then OCF is calculated using moving window average.
OCF = <cos(angle)> ~ time
<cos(angle)>= relaxation_time x time  --(1)
The OCF is used to extimate the relaxation time by curve fitting to Eq. 1. The unit of relaxation time is same as frequency of trajectory samppled. Ex., if the trajectory is written every 0.1 ps and nskip =9 then sampling is done every 1 ps, and the relaxation time would be in ps.

Input files:
Lammps_traj.txt, 9, 0, 2    !!... Name of Trajectory file, No of header lines, No of tail lines, No of columes to be skipped befor xyz coordinates
5, 0            !!... No of trajectories to be sampled, with number of frames to be skipped. For example (nskip =0, all the trajectory will be sampled, =1, every alternet trajectory will be sampled)
165             !!... Total number of atoms
157, 158        !!... Index of atom A, B through with the direction vector would be constructed. 
