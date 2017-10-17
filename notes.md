# Numerical advection of chemical species

- chemical species often corellated
  - e.g. NO\_y (sum of fast-reacting nitrogen species) and nitrous oxide (N\_2O) (plumb2007)

- ozone hole can be measured by a lack of correlation (proffitt1990)
  - ozone loss not seen in Arctic polar vortex because it's masked by transport of ozone-rich air through the region
  - correlations do not change due to advection, only due to diffusion or chemical reactions
  - expect parcels with similar N2O mixing ratios to have similar O3 mixing ratios
  - hence, any loss in O3 is due to chemical processes rather than dynamical processes
  - the authors compared mixing ratios inside and outside polar vortex region and found loss of ozone within vortex

- a "tracer" is a chemical specie, aerosol, water constituent etc
- tracers advected separately, so corellations are not preserved

## mixing scatter plot

- advection schemes can create numerical mixing and numerical unmixing (through numerical dispersion errors)
- advection schemes will always have these errors because they are only discrete approximations
- for a particular scheme, do the numerical errors look like observed, "real mixing"?

- ignore diffusion or chemical reactions for now
- real mixing between two parcels is a straight line
- real mixing between two correlated tracers all the straight lines -> convex hull

- whiteboard: initial relation, () ξ = -8/10 χ^2 + 9/10 (ξ pronounced kzi, χ pronounced kay)
- draw Fig 1 from lauritzen-thuburn2011 piece-by-piece:
  - axes
  - initial curve
  - some initial points on curve
  - straight lines to make convex hull

- animation of test setup

- show some results
  - CSLAM-CN5.5 1.5deg (good)
  - MPAS-CN0.8 1.5deg (bad)

## toy terminator test

- chemical reactions!
- photolysis near the solar terminator, strong spatial gradients of chemical species e.g. stratospheric chlorine, bromine

Consider mixing ratio, X

* dissociation: X\_2 --(k\_1)--> X + X
* combination: X + X --(k\_2)--> X\_2

where k\_1 and k\_2 are reaction rates.
k\_1 is a function of the solar zenith angle, z

    |  *
    |z/
    |/
    +----

(and show heatmap plot of k\_1).  k\_2 is constant.

Total number of atoms is X\_total.  You can show the material derivative is conserved
Hence, if initial condition is constant in space then X\_total is constant time also

X\_total = x + 2 X\_2

- analytic solution is trivial and it doesn't matter about flow or reactions
- show CAM results
