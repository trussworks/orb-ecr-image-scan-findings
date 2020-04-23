# orb-ecr-image-scan-findings

The ECR Image Scan Findings orb source code is housed here.

The orb will use ECR to scan an image and report any findings.

## Usage

For full usage guidelines, see the [orb registry listing](https://circleci.com/orbs/registry/orb/trussworks/orb-ecr-image-scan-findings).

### Expectations

- Used in a repository where an image is being built
- Access to an AWS account that can run ECR on the specified image

### Example

For an example of this orb in use, see the GitHub repo [trussworks-atlantis-ecs-image](https://github.com/trussworks/trussworks-atlantis-ecs-image).

## Developer Setup

Install dependencies

```sh
brew install circleci pre-commit
pre-commit install --install-hooks
```
