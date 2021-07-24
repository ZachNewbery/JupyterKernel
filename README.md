[![Build Status](https://github.com/gap-packages/JupyterKernel/actions/workflows/CI.yml/badge.svg?branch=master)](https://github.com/gap-packages/JupyterKernel/actions?query=workflow%3ACI+branch%3Amaster)
[![Code Coverage](https://codecov.io/github/gap-packages/JupyterKernel/coverage.svg?branch=master&token=)](https://codecov.io/gh/gap-packages/JupyterKernel)
# The JupyterKernel GAP package 

This package implements the [Jupyter](https://www.jupyter.org) protocol in GAP.

## Installation
### Dependencies and GAP installation
Download and unpack the corresponsing archive from the GAP website at

  <https://www.gap-system.org/Releases/>
  
For Windows installations, it is recommended to utilise an installation of
Windows Subsystem for Linux (WSL) as this makes the installation process
much more streamlined. Prior to compiling the GAP system, JupyterKernel
requires the following packages to be installed:

- libzmq3-dev
- m4
        
Which can be installed using your systems package manager. Then, compile
the GAP core system by running

    ./configure; make
            
in the unpacked archive directory. After that, go into the `pkg` subdirectory,
and run

    ../bin/BuildPackages.sh
            
to setup all of the required dependencies for JupyterKernel

### Jupyter Setup
Jupyter can be installed using the following:

    pip3 install notebook
            
Note that a Python version >= 3.5 is required. Once that is done, the GAP 
kernel must be registered with Jupyter, by running the following command 
in the `pkg/JupyterKernel` directory of your GAP installation:

    pip3 install .

or for your user only:

    pip3 install . --user

### Adding JupyterKernel to your PATH
If GAP is not in your PATH, then you have to set the environment variable
`JUPYTER_GAP_EXECUTABLE` to point to your GAP executable for Jupyter to
be able to execute GAP, and the script jupyter-kernel-gap that is
distributed with this package in the directory `bin/` needs to be in
your path.

This can be done through symlinking:

    sudo ln -s <GAP-installation-directory>/bin/gap.sh gap
  
    sudo ln -s <GAP-installation-directory>/pkg/JupyterKernel-1.3/bin/jupyter-kernel-gap

And an export command to set `JUPYTER_GAP_EXECUTABLE`:

    export JUPYTER_GAP_EXECUTABLE=gap

### Running JupyterKernel
With all of the setup complete, a Jupyter notebook can be run with
  
    jupyter notebook
  
and GAP should be able to be chosen as a kernel option.

 
## Documentation

Information and documentation can be found in the manual, available
as PDF `doc/manual.pdf` or as HTML `doc/chap0_mj.html`, or on the package
homepage at

  <http://gap-packages.github.io/JupyterKernel/>

## Bug reports and feature requests

Please submit bug reports and feature requests via our GitHub issue tracker:

  <https://github.com/gap-packages/JupyterKernel/issues>


# License

JupyterKernel is free software; you can redistribute it and/or modify it under
the terms of the BSD 3-clause license.

For details see the files COPYRIGHT.md and LICENSE.

# Acknowledgement

<table class="none">
<tr>
<td>
  <img src="http://opendreamkit.org/public/logos/Flag_of_Europe.svg" width="128">
</td>
<td>
  This infrastructure is part of a project that has received funding from the
  European Union's Horizon 2020 research and innovation programme under grant
  agreement No 676541.
</td>
</tr>
</table>

