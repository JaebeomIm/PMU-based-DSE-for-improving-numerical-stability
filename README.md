# PMU-based-DSE-for-improving-numerical-stability

Bus, branch, generator, and PMU data for Simple 6-bus, IEEE 14-, 118- 1062-bus and Korean 1665-bus systems
Please refer to MATPOWER-manual ver 7.1 in detail.


==========
Bus Data
==========

Columns  1   bus number (positive integer)
Columns  2   bus type (1 = PQ, 2 = PV, 3 = ref, 4 = isolated)
Columns  3   real power demand (MW)
Columns  4   reactive power demand (MVAr)
Columns  5   shunt conductance (MW demanded at V = 1.0 p.u.)
Columns  6   shunt conductance (MW demanded at V = 1.0 p.u.)
Columns  7   area number (positive integer)
Columns  8   voltage magnitude (p.u.)
Columns  9   voltage angle (degrees)
Columns 10   base voltage (kV)
Columns 11   loss zone (positive integer)
Columns 12   maximum voltage magnitude (p.u.)
Columns 13   minimum voltage magnitude (p.u.)
Columns 14   Lagrange multiplier on real power mismatch (u/MW)
Columns 15   Lagrange multiplier on reactive power mismatch (u/MVAr)
Columns 16   Kuhn-Tucker multiplier on upper voltage limit (u/p.u.)
Columns 17   Kuhn-Tucker multiplier on lower voltage limit (u/p.u.)


==========
Branch Data
==========

Columns  1   "from" bus number
Columns  2   "to" bus number
Columns  3   resistance (p.u.)
Columns  4   reactance (p.u.)
Columns  5   total line charging susceptance (p.u.)
Columns  6   MVA rating A (long term rating), set to 0 for unlimited
Columns  7   MVA rating B (short term rating), set to 0 for unlimited
Columns  8   MVA rating C (emergency rating), set to 0 for unlimited
Columns  9   transformer off nominal turns ratio, if non-zero (taps at "from"
	           bus, impedance at "to" bus, i.e. if r = x = b = 0, tap = |Vf|/|Vt|;
	           tap = 0 used to indicate transmission line rather than transformer,
	           i.e. mathematically equivalent to transformer with tap = 1)
Columns 10   transformer phase shift angle (degrees), positive -> delay
Columns 11   initial branch status, 1 = in-service, 0 = out-of-service
Columns 12   minimum angle difference, theta_f - theta_t (degrees)
Columns 13   maximum angle difference, theta_f - theta_t (degrees)
Columns 14   real power injected at "from" bus end (MW)
Columns 15   reactive power injected at "from" bus end (MVAr)
Columns 16   real power injected at "to" bus end (MW)
Columns 17   reactive power injected at "to" bus end (MVAr)
Columns 18   Kuhn-Tucker multiplier on MVA limit at "from" bus (u/MVA)
Columns 19   Kuhn-Tucker multiplier on MVA limit at "to" bus (u/MVA)
Columns 20   Kuhn-Tucker multiplier lower angle difference limit (u/degree)
Columns 21   Kuhn-Tucker multiplier upper angle difference limit (u/degree)


==========
Gen Data
==========

Columns  1   bus number
Columns  2   real power output (MW)
Columns  3   reactive power output (MVAr)
Columns  4   maximum reactive power output (MVAr)
Columns  5   minimum reactive power output (MVAr)
Columns  6   voltage magnitude setpoint (p.u.)
Columns  7   total MVA base of machine, defaults to baseMVA
Columns  8   machine status, > 0 = machine in-service
			                      <= 0 = machine out-of-service
Columns  9   maximum real power output (MW)
Columns 10   minimum real power output (MW)
Columns 11   lower real power output of PQ capability curve (MW)
Columns 12   upper real power output of PQ capability curve (MW)
Columns 13   minimum reactive power output at PC1 (MVAr)
Columns 14   maximum reactive power output at PC1 (MVAr)
Columns 15   minimum reactive power output at PC2 (MVAr)
Columns 16   maximum reactive power output at PC2 (MVAr)
Columns 17   ramp rate for load following/AGC (MW/min)
Columns 18   ramp rate for 10 minute reserves (MW)
Columns 19   ramp rate for 30 minute reserves (MW)
Columns 20   ramp rate for reactive power (2 sec timescale) (MVAr/min)
Columns 21   area participation factor
Columns 22   Kuhn-Tucker multiplier on upper Pg limit (u/MW)
Columns 23   Kuhn-Tucker multiplier on lower Pg limit (u/MW)
Columns 24   Kuhn-Tucker multiplier on upper Qg limit (u/MVAr)
Columns 25   Kuhn-Tucker multiplier on lower Qg limit (u/MVAr)


==========
PMU Data
==========

Columns  1   measurement number
Columns  2   types of measurements (1: bus voltage magnitude, 2: bus voltage phase angle, 3: branch current magnitude, 4: branch current phase angle)
Columns  3   measured value (pu) 
Columns  4   "from" bus number
Columns  5   "to" bus number
Columns  6   branch number
Columns  7   direction of branch (0: no branch, 1: same direction as branch data, 2: opposite direction)
Columns  8   covariance value
Columns  9   area number to which "from" bus belongs
Columns 10   area number to which "to" bus belongs (0: measurement related to bus voltage)
