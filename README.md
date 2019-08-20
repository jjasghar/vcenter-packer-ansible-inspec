# vCenter `packer` `ansible` `inspec`

## Scope

This repo is the core example pipeline bringing vCenter, `packer`,
`ansible` and `inspec` together.

## Process

1) Create a beginning (seed) template. Name it something that is obvious as your "golden" image. I like `debian10-gold` personally.
2) Run the Pipeline to verify that it can build the `master` branch.
3) Create a PR with some changes to the [debian10/playbook.yml](debian10/playbook.yml) and see if your "PR" template is created.
4) Merge the PR into master and see that your seed template is now your changed version.
5) Continue iterating on the `playbook.yml` and you now have a trackable artifact of changes to your templates.

## Usage

### Pre-Reqs

1) `ansible` installed
2) `packer` installed
3) `packer-builder-vphere` installed from [here][builder_vsphere]

### Running the pipeline

1) Clone this repository and make any changes to the [Jenkinsfile](./Jenkinsfile)
2) Take the Jenkinsfile import it into your jenkins instance.
3) Edit the following from the [variables.json](./debian10/variables.json) example
4) Run the pipeline with changes you may want.

## License & Authors

If you would like to see the detailed LICENCE click [here](./LICENCE).

- Author: JJ Asghar <awesome@ibm.com>
- Author: Will Plusnick <pwplusni@us.ibm.com>

```text
Copyright:: 2019- IBM, Inc

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

[builder_vsphere]: https://github.com/jetbrains-infra/packer-builder-vsphere
