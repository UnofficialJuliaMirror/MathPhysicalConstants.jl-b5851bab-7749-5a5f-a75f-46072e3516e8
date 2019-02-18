# MathPhysicalConstants

| **Documentation**                       | [**Package Evaluator**][pkgeval-link] | **Build Status**                          | **Code Coverage**               |
|:---------------------------------------:|:-------------------------------------:|:-----------------------------------------:|:-------------------------------:|
| [![][docs-stable-img]][docs-stable-url] | [![][pkg-0.0.5-img]][pkg-0.0.5-url]       | [![Build Status][travis-img]][travis-url] | [![][coveral-img]][coveral-url] |
| [![][docs-latest-img]][docs-latest-url] | [![][pkg-0.0.6-img]][pkg-0.0.6-url]       | [![Build Status][appvey-img]][appvey-url] | [![][codecov-img]][codecov-url] |

| System | Test Status |
| :----- | :---------: |
| Linux/macOS | [![Travis](https://travis-ci.org/LaGuer/MathPhysicalConstants.jl.svg?branch=master)](https://travis-ci.org/LaGuer/MathPhysicalConstants.jl) |
| Windows | [![AppVeyor](https://ci.appveyor.com/api/projects/status/h2223a8hus4hxam3/branch/master?svg=true)](https://ci.appveyor.com/project/LaGuer/MathPhysicalConstants-jl/branch/master) |
| FreeBSD | [![Cirrus](https://api.cirrus-ci.com/github/LaGuer/MathPhysicalConstants.jl.svg)](https://cirrus-ci.com/github/LaGuer/MathPhysicalConstants.jl) |


[![Julia Observer](https://juliaobserver.com/packages/MathPhysicalConstants)](https://juliaobserver.com/packages/MathPhysicalConstants)

[![Package Evaluator](http://pkg.julialang.org/badges/MathPhysicalConstants_0.6.svg)](http://pkg.julialang.org/detail/MathPhysicalConstants)

[![Build Status](https://api.travis-ci.org/LaGuer/MathPhysicalConstants.jl.svg)](https://travis-ci.org/LaGuer/MathPhysicalConstants.jl)

[![Build status](https://ci.appveyor.com/api/projects/status/h2223a8hus4hxam3/branch/master?svg=true)](https://ci.appveyor.com/project/LaGuer/MathPhysicalConstants-jl/branch/master)

[![Coverage Status](https://coveralls.io/repos/github/LaGuer/MathPhysicalConstants.jl/badge.svg)](https://coveralls.io/github/LaGuer/MathPhysicalConstants.jl)


MathPhysicalConstants is a Julia package which has the values of a range of mathematical and physical constants updated with most recent available dataset from BIPM in 2018. Currently [MKS](https://en.wikipedia.org/wiki/MKS_system_of_units) and [CGS](https://en.wikipedia.org/wiki/Centimetre%E2%80%93gram%E2%80%93second_system_of_units) units and [International System of Units](https://en.wikipedia.org/wiki/International_System_of_Units). Updated CODATA 2017 and redefinition of SI base units following [ISU, BIPM, CGPM, CIPM](https://www1.bipm.org/utils/common/pdf/CGPM-2018/26th-CGPM-Resolutions.pdf) approved resolutions and scheduled to come into force on 20 May 2019.

## Installation

The package can be installed directly from its [github repository](https://github.com/LaGuer/MathPhysicalConstants.jl):

    Pkg.clone("https://github.com/LaGuer/MathPhysicalConstants.jl")

## Usage

Usage is pretty straightforward. Start off by loading the package.

    julia> using MathPhysicalConstants
    
Query and retrieve the Planck Constant using the most updated International System of Units (SI)    
    
    julia> MathPhysicalConstants.SI.PlanckConstantH
    6.62607015e-34
    
    julia> big(MathPhysicalConstants.SI.PlanckConstantH)
    6.62606895999999960651234296395253273824527450725424150396117674176417443843193e-34
    
Now let's have a look at ƛe ≡ ħ/m_e.c the reduced electron radius formula. Try it with BigFloat and Measurement
    
    julia> big(MathPhysicalConstants.SI.PlanckConstantH)/(big(MathPhysicalConstants.SI.MassElectron)*big(MathPhysicalConstants.SI.SpeedOfLight))
    2.42631027637202010003687587191357482878156204816578736228540160944126721996979e-12

Let's switch to Earth's gravitational acceleration in MKS units.

    julia> PhysicalConstants.MKS.GravAccel
    9.80665

Or in CGS units.

    julia> MathPhysicalConstants.CGS.GravAccel
    980.665
    
last but not least in International System of Units (SI)
    
    julia> MathPhysicalConstants.SI.GravAccel
    9.80665
    
Constant List
-------------

    "| Symbol  | Name                                | Formula                  | Dimension      | Value              | Unit            |\n",
    "| ------  | ----                                | -------                  | ---------      | -----              | ----            |\n",
    "| `π`     | pi                                  | -                        | -              | 3.1415926535897932 | `pure number`   |\n",
    "| `e`     | Euler's number                      | -                        | -              | 2.7182817284590452 | `pure number`   |\n",
    "| `γ`     | euler_gamma                         | -                        | -              | 0.5772156649015329 | `pure number`   |\n",
    "| `26SGP` | 26 sporadic group Product           | -                        | -              | exp(841.2869278)   | `pure number`   |\n",
    "| `HFP`   | Happy Family product                | -                        | -              | exp(674.5210288)   | `pure number`   |\n",
    "| `O_M`   | Monster Group Cardinal              | -                        | -              | 8.080174248 × 1053 | `pure number`   |\n",
    "| `O_B`   | Baby Monster Group Cardinal         | -                        | -              | 4.15478148 × 1033  | `pure number`   |\n",
    "| `c`     | Speed of light in vacuum            | -                        | -              | 2.99792458e8       | `m.s^-1`        |\n",
    "| `ħ`     | Reduced Planck constant             | ħ=h/2pi                  | -              | 1.054571800e-34    | `m^2 kg s^-1`   |\n",
    "| `G'`    | constant of gravitation CODATA2014  | -                        | M^-1L^3T^-2    | 6.67408(31)e-11    | `m^3 kg^-1 s^-2`|\n",
    "| `G`     | F.M.Sanchez constant of gravitation | F_gr=Gmm'/ d^2           | M^-1L^3T^-2    | 6.675453818e-11    | `m^3 kg^-1 s^-2`|\n",
    "| `a`     | Electric constant                   | a=α^-1  F_qq=ħc/ad^2     | dimensionless  | 137.035999139^-1   | `pure number`   |\n",
    "| `R_U`   | Universe Hubble radius (Sz)         | R_U=2G.M_U/c)^2          | L              | 1.3065e26          | `m`             |\n",
    "| `G_F`   | Fermi Coupling Constant (Sz)        | G_F=(ħc)^3/E_F^2         |   ML^5T^-2     | 1.4358509(7)e-62   | `J.m^3`         |\n",
    "| `a_G`   |Gravit Sanchez Coupling Constant     | a_G=ħc/Gm_pm_H           | -              | 1.691936465e38     | `pure number`   |\n",
    "| `M_U`   | Universe Sanchez Mass               | M_U=(ħc/G)^2/m_e.m_p.m_H | M              | 8.7936e52          | `kg`            |\n",
    "| `t_cc`  | Kotov Cosmic Periodicity            | -                        | s              | 9600.061(2)        | `s`             |\n",
    "|`r_H(0)` | Bare Hydrogen radius                |    aħ/m_ec               | L              | 5.291772103e-11    | `m`             |\n",
    "| `H`     |Hydrogen-electron mass ratio         |    m_H/m_e               | dimensionless  | 1837.152645        | `m_e`           |\n",
    "| `p`     |Proton-electron mass ratio           |    m_p/m_e               | dimensionless  | 1836.152672        | `m_e`           |\n",
    "| `n`     |Neutron-electron mass ratio          |    m_n/m_e               | dimensionless  | 1838.683659        | `m_e`           |\n",
    "| `m_e`   |electron mass                        | -                        | M              |9.10938356(11)e-31  | `kg`            |\n",
    "| `μ'`    |Muon electron mass ratio CODATA2014  | -                        | dimensionless  |206.7682826(41)     | `m_e`           |\n",
    "| `μ`     |Muon mass F.M.SANCHEZ  (Sz)          | -                        | dimensionless  |206.7682869         | `m_e`           |\n",
    "| `f'`    |Strg Nuc Coupling Constant CODATA2014| -                        | dimensionless  |1/0.1181(11)        | `pure number`   |\n",
    "| `f`     |Strg Nuc Coupling Constant C.Bizouard|    F^2/2pi(pH)^3/2       | dimensionless  |8.434502892         | `pure number`   |\n",
    "| `F'`    |Fermi Constant reduced mass CODAT2014|   E_F / m_ec^2           | dimensionless  |573007.33(25)       | `pure number`   |\n",
    "| `F`     |Fermi Constant reduc mass F.M.SANCHEZ| -                        | dimensionless  |573007.3652         | `pure number`   |\n",
    "| `d_e`   | electron magnetic moment excess     | -                        | dimensionless  |1.00115965218091(26)| `pure number`   |\n",
    "| `θ'`    |CMB Temperature CODATA2014           | -                        | -              |  2.7255(6) K       | `K`             |\n",
    "| `θ`     |CMB Temperature F.M.Sanchez          | -                        | -              |  2.725820831 K     | `K`             |\n",
    "| `k_B`   |Boltzman Energy-temperature Convers° | -                        | -              | 1.3806488e10-23    | `J K^-1`        |\n",
    "| `W`     |Intermed vector boson Red. Mass      | -                        | dimensionless  | 157298(23)         | `pure number`   |\n",
    "| `W_s`   |Intermed vector boson Red. Mass Sz   | -                        | dimensionless  | 157340             | `pure number`   |\n",
    "| `Z`     |Intermediate vector boson Red. Mass  | -                        | dimensionless  | 178450.0(41)       | `pure number`   |\n",
    "| `Z_s`   |Intermed vector boson Red. Mass Sz   | -                        | dimensionless  | 178452             | `pure number`   |\n",
    "| `Π±`    |Intermediate vector boson Red. Mass  | -                        | dimensionless  | 273.13203(68)      | `pure number`   |\n",
    "| `Π0`    |Intermediate vector boson Red. Mass  | -                        | dimensionless  | 264.1426(18)       | `pure number`   |\n",
    "\n",

License
-------

The `MathPhysicalConstants.jl` package is licensed under the MIT "Expat" License.  The
original author is La Guer.

Please, cite this paper (http://vixra.org/abs/1811.0146v8) if you
employ this package in your research work.


[docs-latest-img]: https://img.shields.io/badge/docs-latest-blue.svg
[docs-latest-url]: https://LaGuer.github.io/MathPhysicalConstants.jl/latest/

[docs-stable-img]: https://img.shields.io/badge/docs-stable-blue.svg
[docs-stable-url]: https://LaGuer.github.io/MathPhysicalConstants.jl/stable/

[pkgeval-link]: http://pkg.julialang.org/?pkg=MathPhysicalConstants

[pkg-0.5-img]: http://pkg.julialang.org/badges/MathPhysicalConstants.0.5.svg
[pkg-0.5-url]: http://pkg.julialang.org/detail/MathPhysicalConstants.html
[pkg-0.6-img]: http://pkg.julialang.org/badges/MathPhysicalConstants.0.6.svg
[pkg-0.6-url]: http://pkg.julialang.org/detail/MathPhysicalConstants.html

[travis-img]: https://travis-ci.org/LaGuer/MathPhysicalConstants.jl.svg?branch=master
[travis-url]: https://travis-ci.org/LaGuer/MathPhysicalConstants.jl

[appvey-img]: https://ci.appveyor.com/api/projects/status/u8mg5dlhyb1vjcpe?svg=true
[appvey-url]: https://ci.appveyor.com/project/LaGuer/mathphysicalconstants-jl

[coveral-img]: https://coveralls.io/repos/github/LaGuer/MathPhysicalConstants.jl/badge.svg?branch=master
[coveral-url]: https://coveralls.io/github/LaGuer/MathPhysicalConstants.jl?branch=master

[codecov-img]: https://codecov.io/gh/LaGuer/MathPhysicalConstants.jl/branch/master/graph/badge.svg
[codecov-url]: https://codecov.io/gh/LaGuer/MathPhysicalConstants.jl
