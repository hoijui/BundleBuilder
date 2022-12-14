<!--
SPDX-FileCopyrightText: 2022 Robin Vobruba <hoijui.quaero@gmail.com>

SPDX-License-Identifier: CC0-1.0
-->

# IoPA OKH-LOSH Bundle-Builder

[![GitHub license](
    https://img.shields.io/github/license/hoijui/BundleBuilder.svg?style=flat)](
    ./LICENSE)
[![REUSE status](
    https://api.reuse.software/badge/github.com/hoijui/BundleBuilder)](
    https://api.reuse.software/info/github.com/hoijui/BundleBuilder)

CLI tool that takes an OKH-LOSH RDF manifest as input,
and generates a bundle from it.
A Bundle is either a folder on the FS or a zip file,
each respectively containing the manifest file
and all the files linked to by it.

## Usage

There are three options for a valid input,
and two for a valid output

### 1. local manifest file

```shell
wget https://gitlab.opensourceecology.de/verein/projekte/losh-rdf/-/raw/main/RDF/wikifactory.com/@rwbowman/openflexure-microscope/project.ttl
python3 man2bndl.py project.ttl bundle/
```

## 2. URL to manifest file

```shell
python3 man2bndl.py \
    https://gitlab.opensourceecology.de/verein/projekte/losh-rdf/-/raw/main/RDF/wikifactory.com/@rwbowman/openflexure-microscope/project.ttl \
    bundle/
```

### 3. Project web hosting URL

```shell
python3 man2bndl.py https://wikifactory.com/@rwbowman/openflexure-microscope \
    bundle/
```

### ZIP instead of directory output

Though, the output can not only be a folder like in the above examples,
but also a ZIP file;
the `.zip` suffix is required in this case:

```shell
python3 man2bndl.py project.ttl bundle.zip
```
