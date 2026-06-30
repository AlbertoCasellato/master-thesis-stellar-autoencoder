# Preprocessing

## Load Profiles and Resample to Fixed Grid

The objective is to save just one big dataset of all the stellar profiles of a fixed metallicity.
The first dimension of the dataset is a list of all the timesteps of each star with different mass, the second dimension is the number of equidistant sampled points along the radius of the star, and the third dimension are the important features of each star (radius, temperture, density, gravitational energy) resampled on the equidistant points along the radius.

I looped every F81 file in the directory for stars with Z=0.02 and no rotation and:

1. I used the mass as the main coordinate that initially was in the profiles with values from 1 to 0, and here is inverted (from 0 to 1).
2. each feature has been resampled on different mass points that are equidistant each other
3. each profile for every timestep of each star is then concatenated in the variable X, and a list "star_id" contains the initial mass of each star, each mass value repeated based on the number of timesteps of each star.

## Log Scaling
