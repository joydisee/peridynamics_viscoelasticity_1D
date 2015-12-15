# Peridynamics (PD)


## PD_deck class

Open a python terminal or create a python script in the folder where the `deck.py` file is:

`from deck import PD_deck` will import the *PD_deck* class.

`data = PD_deck()` will create an object called `data` having the variables and methods of the *PD_deck* class. To create that object, the class will import data from the `deck.xml` file. It is necessary to properly fill it. The following sections explain how to do so.

It is possible to check the data currently loaded in the class using, for example, `data.Final_time` will show you the total duration of the simulation, or `data.Num_Nodes` to see how many PD nodes there are.

#### Variables

* `PD_deck.Horizon_Factor:` Horizon = Horizon\_Factor X `PD_deck.Delta_x` X `Safety parameter`

`Safety parameter:` 1.01


* `PD_deck.N_Delta_t:` Total number of timesteps.

* `PD_deck.Final_Time:` Total duration of the simulation.

* `PD_deck.N_Delta_x:` Total number of spatial steps.

* `PD_deck.Length:` Length of the 1D bar.

* `PD_deck.Num_Nodes:` Total number od PD nodes.

* `PD_deck.Delta_x:` Spatial step.

* `PD_deck.Length_Tot:` Length of the bar specified by the user + additional nodes to apply the load.

* `PD_deck.x:` Vector x containing the positions of the PD nodes centered around 0 and separated by a constant distance `PD_deck.Delta_x`.

* `PD_deck.Influence_Function:` Value fo the influence function provided in `deck.xml`

* `PD_deck.Loading_Flag:` Loading scheme selected by the user.

* `PD_deck.Material_Flag:` Material behaviour selected by the user.

## Example of XML deck

```XML
<?xml version="1.0"?>
<data>
	<Discretization>
			<N_Delta_x>4</N_Delta_x>
			<N_Delta_t>2</N_Delta_t>
			<Final_Time>1.0</Final_Time>
			<Horizon_Factor>1</Horizon_Factor>
			<Influence_Function>1</Influence_Function>
	</Discretization>
	<Boundary_Conditions>
	        <Type>RAMP</Type>
			<Force>54.0</Force>
			<Ramp_Time>1.0</Ramp_Time>
	</Boundary_Conditions>
	<Geometry>
			<Length>4.0</Length>
			<Surface>1</Surface>
	</Geometry>
	<Material>
	        <Type>ELASTIC</Type>
			<E_Modulus>4000.0</E_Modulus>
	</Material>
</data>
```

`<Discretization>` must contain:

* `<N_Delta_x>` The number of spatial steps.
* `<N_Delta_t>` The number of time steps.
* `<Final_Time>` Duration of the simulation.
* `<Influence_Function>` The value of the influence function as defined in Silling, Lehoucq 2010.

`<Boundary_Conditions>` must contain:

* `<Type>` Currently, only the `RAMP` loading type is available.
    * `<Force>` Force applied on the bar on its extremeties.
    * `<Ramp_Time>` Time during which the force grows linearly before reaching the force value.

`<Geometry>` must contain:

* `<Length>` Lenth of the 1D bar.
* `<Surface>` Surface occupied by the 1D bar (perpendicular to the bar's direction).

`<Material>` must contain:

* `<Type>` Currently, only the `ELASTIC` material is avilable.
    * `<E_Modulus>` Value of the 1D elastic modulus.
*
