# Peridynamics


##PD_deck class

* `PD_deck.Horizon_Factor:` The horizon factor parameter

* `PD_deck.N_Delta_t:`

* `PD_deck.Length:` Length of the 1D bar. 

##Example of XML deck

```XML
<?xml version="1.0"?>
<data>
	<Discretization>
			<N_Delta_x>4</N_Delta_x>
			<N_Delta_t>3</N_Delta_t>
			<Final_Time>1.5</Final_Time>
			<Horizon_Factor>1</Horizon_Factor>
			<Influence_Function>1</Influence_Function>
	</Discretization>
	<Boundary_Conditions>
			<Force>54.0</Force>
			<Ramp_Time>1.0</Ramp_Time>
	</Boundary_Conditions>
	<Geometry>
			<Length>4.0</Length>
			<Surface>1</Surface>
	</Geometry>
	<Material>
			<E_Modulus0>4000.0</E_Modulus0>
			<E_Modulus1>0.0</E_Modulus1>
			<Relaxation_Time0>NaN</Relaxation_Time0>
			<Relaxation_Time1>88.74</Relaxation_Time1>
	</Material>
</data>
```
