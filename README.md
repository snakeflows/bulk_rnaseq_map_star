<!--
SPDX-FileCopyrightText: © 2026 Marcel Schilling <mschilling@idibell.cat>
SPDX-License-Identifier: FSFAP
-->


[#]: # (#######)
[#]: # ( About )
[#]: # (#######)

[#]: # (File:    README.md)
[#]: # (Author:  Marcel Schilling <mschilling@idibell.cat>)
[#]: # (Created: 2026-10-26)
[#]: # (License: GNU All-Permissive License)
[#]: # (Purpose: README Markdown file for the bulk RNA-seq genome mapping
[#]: #           \(STAR\) Snakemake workflow.)


[#]: # (#########)
[#]: # ( License )
[#]: # (#########)

[#]: # (README Markdown file for the bulk RNA-seq genome mapping \(STAR\))
[#]: # (Snakemake workflow.)
[#]: # (Copyright \(C\) 2026  Marcel Schilling)
[#]: #
[#]: # (Copying and distribution of this file, with or without modification,)
[#]: # (are permitted in any medium without royalty provided the copyright)
[#]: # (notice and this notice are preserved.  This file is offered as-is,)
[#]: # (without any warranty.)


[#]: # (########)
[#]: # ( README )
[#]: # (########)

# Bulk RNA-seq genome mapping \(STAR\) Snakemake workflow.

A [Snakemake][snakemake] [workflow][snakemake-workflow-catalog] to map
bulkRNA-seq reads to a genome using [STAR][star].

**Note: This workflow is currently under development**.


---
## Table of contents

* [License](#license)
* [Usage](#usage)
* [Installation](#installation)
* [Citation](#citation)
---


## License

Copyright © 2026  [Marcel Schilling](mailto:mschilling@idibell.cat)

This program is free software: you can redistribute it and/or modify it under
the terms of the GNU Affero General Public License as published by the Free
Software Foundation, either version 3 of the License, or (at your option) any
later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE.
See the GNU Affero General Public License for more details.

You should have received [a copy of the GNU Affero General Public
License](LICENSES/AGPL-3.0-or-later.txt) along with this program.
If not, see <https://www.gnu.org/licenses/>.


## Usage

The usage of this workflow should eventually be described in the [Snakemake
Workflow Catalog][workflow-usage-in-snakemake-workflow-catalog].

**Note: The above link won't work until initial publication of the workflow and
its subsequent inclusion in the [Snakemake Workflow
Catalog][snakemake-workflow-catalog].**

In short:

1. Adjust [the `config.yaml` file in the `config`
   directory](config/config.yaml) to your needs 
   \[**TODO:** documentation still missing\].
2. Run `snakemake` from the workflow's root directory.

Note that depending on the specific environment, `snakemake` might require
additional parameters (like [`--cores`][snakemake-cores] for running on locally
on the same machine or [`--profile`][snakemake-profile] to submit jobs to
cluster nodes via a scheduler or run in the cloud.
Please refer to [the Snakemake documentation][snakemake-cli] for details.

If you want to use this workflow as a [module][snakemake-modules] in your own
Snakemake workflow, see [the corresponding documentation][snakemake-modules] for
instructions.


## Installation

This workflow is based on [Snakemake][snakemake] and obtains all of its other
dependencies via [Conda][conda] (which also provides [Snakemake][snakemake]
itself).
It was developed/tested on 64-bit GNU/Linux \[**TODO:** Package pinnings still
missing\].

For detailed documentation regarding the use of Snakemake workflows, see [the
Snakemake Workflow Catalog documentation][snakemake-workflow-catalog-usage] and
specifically [the deployment section for this
workflow][snakemake-workflow-catalog-deploy].

In short:

1. [Install][conda-install] [Conda][conda]:

   ```sh
   bash <(curl 'https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Linux-x86_64.sh')
   ```

2. [Install][snakemake-install] [Snakemake][snakemake]:

   ```sh
   conda create -c conda-forge -c bioconda -n snakemake snakemake
   conda activate snakemake
   ```

3. Create a local copy of [the workflow][workflow-repo]:

   ```sh
   git clone 'https://github.com/snakeflows/bulk_rnaseq_map_star.git'
   cd bulk_rnaseq_map_star
   ```

   , or deploy [the workflow][workflow-repo] as [a module][snakemake-modules]
   via [Snakedeploy][snakedeploy]:


   ```sh
   mkdir bulk_rnaseq_map_star
   cd bulk_rnaseq_map_star
   snakedeploy deploy-workflow \
     'https://github.com/snakeflows/bulk_rnaseq_map_star.git'
   ```


## Citation

This workflow is unpublished so far.
If you use it for your research, please consider citing [the workflow's
repository][workflow-repo] in the meantime.



[#]: # (############)
[#]: # ( References )
[#]: # (############)

[snakemake]: https://snakemake.github.io "Snakemake home page"
[snakemake-workflow-catalog]: https://snakemake.github.io/snakemake-workflow-catalog/ "Snakemake Workflow Catalog"
[star]: http://alexdobin.github.io/STAR/ "STAR on GitHub Pages"
[workflow-usage-in-snakemake-workflow-catalog]: https://snakemake.github.io/snakemake-workflow-catalog/docs/workflows/snakeflows%20bulk_rnaseq_map_star "Workflow usage documentation in the Snakemake Workflow Catalog"
[snakemake-cores]: https://snakemake.readthedocs.io/en/stable/executing/cli.html#useful-command-line-arguments "Snakemake --cores parameter documentation"
[snakemake-profile]: https://snakemake.readthedocs.io/en/stable/executing/cli.html#profiles "Snakemake --profile parameter documentation"
[snakemake-cli]: https://snakemake.readthedocs.io/en/stable/executing/cli.html "Snakemake CLI documentation"
[snakemake-modules]: https://snakemake.readthedocs.io/en/stable/snakefiles/modularization.html#snakefiles-modules "Snakemake Modules documentation"
[snakemake-workflow-catalog-usage]: https://snakemake.github.io/snakemake-workflow-catalog/docs/catalog.html#using-workflows "Snakemake Workflow Catalog usage"
[snakemake-workflow-catalog-deploy]: https://snakemake.github.io/snakemake-workflow-catalog/docs/workflows/snakeflows%20bulk_rnaseq_map_star#deployment "Deployment of the workflow from the Snakemake Workflow Catalog"
[conda-install]: https://docs.conda.io/docs/user-guide/install "Conda install guide"
[conda]: https://conda.io "Conda home page"
[snakemake-install]: https://snakemake.readthedocs.io/en/stable/getting_started/installation.html#full-installation "Snakemake install guide"
[snakedeploy]: https://snakedeploy.readthedocs.io/ "Snakedeploy home page"
[workflow-repo]: https://github.com/snakeflows/bulk_rnaseq_map_star "Workflow repository"
