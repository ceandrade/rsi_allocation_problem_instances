Instances for Root Sequence Index (RSI) Allocation Problem
===============================================================================

<table>
<tr>
  <td>License</td>
  <td>
    <a href="https://github.com/ceandrade/rsi_allocation_problem_instances/blob/master/LICENSE.md">
    <img src="https://img.shields.io/badge/license-BSD--like-blue" alt="License" />
    </a>
  </td>
</tr>
</table>

This project contains instances (test cases) for the
Root Sequence Index (RSI) Allocation Problem also know as
[RSI assigment](http://www.techplayon.com/5g-nr-physical-cell-id-pci-planning)
on 5G networks.


:black_nib: License and Citing
--------------------------------------------------------------------------------

This project uses a permissive BSD-like license and it can be used as it
pleases you. And since this framework is also part of an academic effort, we
kindly ask you to remember to cite the originating paper of this work.
Indeed, Clause 4 estipulates that "all publications, softwares, or any other
materials mentioning features or use of this software (as a whole package or
any parts of it) and/or the data used to test it must cite the following
article explicitly":

> M. Londe, C.E. Andrade, L.S. Pessoa. Exact and heuristic approaches for 
> the root sequence index allocation problem. Applied Soft Computing, 
> page 109634. 2022,
> DOI [10.1016/j.asoc.2022.109634](https://doi.org/10.1016/j.asoc.2022.109634).

[Check it out the full license.](https://github.com/ceandrade/rsi_allocation_problem_instances/blob/master/LICENSE.md)

:books: Instances
-------------------------------------------------------------------------------

The RSI instances are divided into two large groups:

- Long preamble: for these instances, it is accepted to use RSIs from 0 to 839;
- Short preamble: in these instances, RSIs are in the range 0 to 139;

The naming convention is the following: `<group>_n<number of nodes>_r<mininum
RSI distance>_<maximum RSI distance>.{dat, txt, json}`. For example,
`long_n0030_r030_150.dat` indicates a long preamble instance with 30 nodes such
that the minimum allowed RSI distance is 30, and the maximum allowed RSI
distance is 150. In this case, this is a "dat" file that can be read for most
commercial MIP solvers, such as IBM ILOG CPLEX.

All instances have the following fields:

- `instance_name`: a string with the instance name;
- `istance_group`: either "long" or "short" preamble;
- `rsi_range`: two positive integers indicating the range from where RSIs
  should be pulled;
- `rsi_min_max_distance`: the minimal and maximal RSI distance allowed between
  neighboring cells. Note that is `rsi_max_distance` is equal to 139 (for short
  preambles) or 839 (for long preambles), we have no maximal distance;
- `num_nodes`: number of nodes or radios in the network;
- `original_rsis`: the original RSIs assigned to these nodes;
- `num_neighbors`: number of edges between the nodes;
- `neighbors`: a num_neighbors X 2 matrix that indicates each edge of the
  neighboring graph.

Files with extension ".dat" can be read directly for most commercial MIP
solvers such as IBM ILOG CPLEX. Files ending in ".json" are in the famous
JavaScript Object Notation, which can be easily read by most programming
languages such as C++ (using (https://github.com/nlohmann/json)) or Python.
Finally,  files ending on ".txt" are plain text files for easy parsing.

