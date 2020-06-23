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

Install dependencies:

```sh
brew install circleci pre-commit
pre-commit install --install-hooks
```

## Testing Changes

After making changes to `orb.yml` and assuming you have the right credentials,
you should be able to validate your changes:

```sh
circleci orb validate orb.yml
```

Once the validation is crystal, we can then publish a dev version to test with:

```sh
circleci orb publish orb.yml trussworks/orb-ecr-image-scan-findings@dev:first
```

Use this dev version to test in
[trussworks-atlantis-ecs-image](https://github.com/trussworks/trussworks-atlantis-ecs-image)
by creating a new branch and replacing the production version with your dev version.
Commit and push this change. Confirm the CircleCI build was successful.

If the build wasn't successful, edit the necessary changes to `orb.yml` and publish
a new dev version. Repeat until the CircleCI build runs smoothly.

### Merging Changes

Create a PR in here to review your changes. Create another PR in
[trussworks-atlantis-ecs-image](https://github.com/trussworks/trussworks-atlantis-ecs-image)
to verify that the orb is in working condition.

With your PR in this repo approved, you can publish the production version of your
changes to the orb

```sh
circleci orb publish promote sandbox/hello-world@dev:first patch
```

The orb version displayed in the CircleCI orb registry should replace
the orb in the
[trussworks-atlantis-ecs-image](https://github.com/trussworks/trussworks-atlantis-ecs-image)
PR.

Merge the pull requests.
