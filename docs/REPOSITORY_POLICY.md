# TUDa-HWAI GitHub Repository Management Policy

**Language: English (Default) | [简体中文](./REPOSITORY_POLICY.zh-CN.md)**

**Hardware for Artificial Intelligence (HWAI)**  
**Technische Universität Darmstadt**

**Version:** 1.0  
**Scope:** All repositories hosted under the `TUDa-HWAI` GitHub Organization.

---

## 1. General Principles

The TUDa-HWAI GitHub Organization serves as the official platform for hosting, publishing, and maintaining research software developed by the HWAI research group.

All repositories should adhere to the following principles:

- **Professionalism:** Repositories must be clearly named, documented, and organized.
- **Reproducibility:** Published research code should enable independent reproduction of the reported methods and results.
- **Transparency:** Research outputs must be accurately described and properly attributed.
- **Security:** Sensitive information, confidential data, and credentials must never be publicly disclosed.
- **Long-term Maintenance:** Research artifacts should remain accessible and usable after the original contributors leave the group.

## 2. Repository Creation and Approval

### 2.1 Ownership

- All official HWAI research repositories must be created under the `TUDa-HWAI` Organization.
- Each repository must have one designated **Repository Maintainer** responsible for its content and maintenance.
- At least one additional HWAI member should have sufficient access to maintain the repository when the primary maintainer is unavailable.
- Organization Owner permissions should be restricted to authorized group administrators.

### 2.2 Approval

Before creating a new official repository, the researcher should obtain approval from the PI or a delegated Organization Owner.

The request should specify:

- Proposed repository name
- Project or paper title
- Responsible researcher(s)
- Repository visibility: Private or Public
- Publication or release status
- Intended software license

### 2.3 Repository Naming

Repository names must be descriptive, concise, and stable.

Recommended examples:

- `Basis_Sharing`
- `CompressKV`
- `NN2Logic`
- `DiffLUT-Network`

Avoid:

- Temporary names such as `test123`, `new-project`, or `final-code`
- Personal names unrelated to the research project
- Names that misleadingly imply conference acceptance
- Unnecessary renaming after public release

Existing repository names should be preserved to maintain the validity of published paper links.

## 3. Repository Visibility and Publication

### 3.1 Private Repositories

- New projects should normally begin as Private.
- Code associated with submissions under review must follow the relevant conference's anonymity and disclosure policies.
- Unpublished or confidential results must not be made public without authorization.

### 3.2 Public Repositories

Before changing a repository to Public:

1. Obtain approval from the PI or delegated authority.
2. Confirm that code, data, models, and dependencies may legally be distributed.
3. Review the entire Git history for confidential information and credentials.
4. Complete the required repository documentation.
5. Verify that the code and installation instructions work.
6. Confirm that public release does not violate conference, institutional, contractual, or intellectual-property requirements.

Publication status must never be misrepresented.

## 4. Repository Metadata

Every public research repository must include the following metadata.

### 4.1 Description

Use the following format for accepted or published papers:

`[Venue Year] Official Paper Title`

Example:

`[AICAS 2024] Early-Exit with Class Exclusion for Efficient Inference of Neural Networks`

For unpublished work, use the project or paper title without an unconfirmed venue.

### 4.2 Website

Link to the most appropriate official resource:

- Published paper DOI or publisher page
- OpenReview page
- arXiv preprint
- Official project website

### 4.3 Topics

Add approximately 4–6 relevant GitHub Topics.

Examples:

`large-language-models`, `model-compression`, `fpga`, `hardware-acceleration`, `efficient-inference`, `neural-networks`

Topics should accurately reflect the repository's technical contributions.

## 5. Required Repository Files

Every public research repository must include the following files, when applicable.

| File | Purpose |
|---|---|
| `README.md` | Project introduction, installation, usage, and reproducibility |
| `LICENSE` | Legal terms governing code reuse |
| `CITATION.cff` | Citation metadata for software and associated papers |
| `requirements.txt`, `environment.yml`, or equivalent | Dependency specifications |
| `.gitignore` | Exclusion of generated files, credentials, and temporary data |

Recommended additional files:

| File | Purpose |
|---|---|
| `CONTRIBUTING.md` | Contribution and review guidelines |
| `SECURITY.md` | Security reporting policy |
| `CHANGELOG.md` | Record of significant updates |
| `.github/workflows/` | Automated testing and code quality checks |
| `examples/` | Minimal executable examples |
| `configs/` | Reproducible experiment configurations |

### 5.1 README Requirements

Every README must clearly provide:

1. Project title and concise overview
2. Paper title, authors, and publication information, when applicable
3. Installation instructions and dependencies
4. Dataset acquisition and preparation instructions
5. Training, evaluation, or inference commands
6. Expected outputs or representative results
7. Hardware and software requirements
8. Citation instructions
9. License information and support channel

If some experiments cannot be reproduced with publicly available resources, these limitations must be explicitly documented.

## 6. Research Reproducibility

Research repositories must provide sufficient information for other researchers to understand and evaluate the work.

For machine learning projects, this should include:

- Model architecture and implementation details
- Dataset names, sources, versions, and preprocessing
- Training and evaluation configurations
- Random seeds and relevant reproducibility settings
- Software framework and dependency versions
- CUDA, GPU, FPGA, or other hardware requirements, as applicable
- Commands to reproduce the main experiments
- Expected metrics and any known deviations or limitations

Large datasets, model checkpoints, and generated artifacts should be distributed through appropriate storage services rather than committed directly to Git.

When full training is too computationally expensive, maintainers must provide at least a tested minimal example and clearly document the resources required for full reproduction.

## 7. Citation and Licensing

### 7.1 Citation

All repositories associated with research publications must include a valid `CITATION.cff` file.

- Accepted papers should reference their verified publication metadata.
- Published papers should use the official DOI where available.
- Unpublished work must not claim acceptance by a conference or journal.
- The preferred citation should be updated after publication.
- Author names, ordering, titles, and publication identifiers must be checked for accuracy.

### 7.2 Licensing

Every publicly released code repository must have an explicitly approved license.

- The license must comply with university, funding, collaboration, and third-party requirements.
- The repository maintainer must obtain approval before choosing or changing the license.
- Third-party code must retain all required copyright notices and attribution.
- Model weights and datasets may require separate usage terms.

A public repository must not be assumed to be freely reusable simply because its source code is accessible.

## 8. Code Development and Review

### 8.1 Branch Management

- `main` is the stable default branch.
- New features and nontrivial fixes should be developed in dedicated branches.
- Pull Requests should be used for significant changes.
- Direct pushes to protected branches should be restricted.
- Force-pushing or deleting protected branches should be prohibited unless specifically authorized.

### 8.2 Pull Request Review

For substantial changes:

- At least one authorized reviewer should approve the Pull Request.
- Changes should be tested before merging.
- The Pull Request description should explain the purpose and impact.
- Updates affecting published results must receive additional review from the responsible researcher.

### 8.3 Commit Practices

Use clear, descriptive commit messages, for example:

- `Add training scripts for ImageNet experiments`
- `Fix attention mask in inference pipeline`
- `Update README with evaluation instructions`
- `Add citation metadata for accepted paper`

Avoid vague messages such as `update`, `fix`, or `final version`.

## 9. Security and Access Control

- Organization membership and repository permissions must follow the principle of least privilege.
- Administrative access must be limited to authorized maintainers.
- Two-factor authentication is strongly recommended for all contributors and should be enforced after an organization-wide readiness review.
- API keys, passwords, access tokens, SSH private keys, personal information, and confidential datasets must never be committed.
- Credentials must be managed through approved secrets-management mechanisms.
- Accidental credential exposure must be reported immediately, and affected credentials must be revoked or rotated.
- Repository deletion, ownership transfer, and public/private visibility changes require explicit Owner approval.

External contributions and automated workflows must be reviewed according to the project's security requirements.

## 10. Publication Releases and Versioning

When code is officially released alongside a paper:

1. Create a GitHub Release identifying the corresponding code version.
2. Record the relevant paper version or publication status.
3. Include a concise description of supported experiments.
4. Tag a stable version, such as `v1.0.0` or `paper-release-v1`.
5. Preserve the published release whenever possible.

Subsequent major changes should be documented.

A paper's original experimental implementation should remain traceable, even when the repository continues to evolve.

## 11. Repository Maintenance and Archiving

### 11.1 Active Projects

Each active repository must have an identified maintainer.

Maintainers should:

- Respond to relevant Issues when practical.
- Keep documentation accurate.
- Review security and dependency concerns.
- Update reproduction instructions when necessary.

### 11.2 Researcher Departure

Before a researcher leaves HWAI:

- Transfer repository maintenance responsibilities.
- Document outstanding issues and important configurations.
- Ensure that required code, documentation, and approved research artifacts are accessible to the group.
- Revoke access that is no longer needed.

### 11.3 Inactive Projects

Repositories that are no longer maintained may be archived with approval.

Published research repositories should generally remain publicly accessible for long-term reproducibility.

Deleting, renaming, or transferring a published repository requires an explicit review of its academic references and existing links.

## 12. Compliance and Exceptions

Repository maintainers are responsible for ensuring compliance with this policy.

The PI or a delegated Organization Owner may approve documented exceptions when justified by:

- Research confidentiality
- Publication requirements
- Intellectual-property constraints
- Security restrictions
- Project-specific technical limitations

Exceptions must not compromise the security of the Organization or misrepresent published research results.

---

## Appendix: New Repository Release Checklist

Before a repository is made Public, confirm:

- [ ] Repository name and description are correct.
- [ ] PI or delegated authorization has been obtained.
- [ ] Publication and intellectual-property restrictions have been checked.
- [ ] README contains working installation and usage instructions.
- [ ] Dependencies and environment versions are documented.
- [ ] Main experiments or minimal examples have been tested.
- [ ] Paper metadata and `CITATION.cff` are correct.
- [ ] License and third-party attribution have been approved.
- [ ] No secrets, confidential information, or prohibited data are present.
- [ ] At least one responsible maintainer is assigned.
- [ ] Appropriate repository permissions and branch protections are configured.
- [ ] Official publication release or version tag is prepared when applicable.

**A research repository should only be publicly released after the required checks have been completed and approved.**

---

*Hardware for Artificial Intelligence (HWAI) · Technische Universität Darmstadt*
