# Repomix Issue #937 - .ignore File Support Test

This repository is created to reproduce and test [repomix issue #937](https://github.com/yamadashy/repomix/issues/937).

## Issue Description

In repomix v1.9.0, `.ignore` file support was implemented, but it doesn't work as expected. Files specified in `.ignore` are still being included in the repomix output.

## Test Setup

- **File to be ignored**: `spec/data/openaip/de_apt.json`
- **Ignore pattern**: `spec/data/` (specified in `.ignore` file)
- **Expected behavior**: The JSON file should be excluded from repomix output
- **Actual behavior**: The JSON file is included in repomix output (issue reproduced)

## CI Workflow

The GitHub Actions workflow (`test-repomix-ignore.yml`) will:

1. Install repomix v1.9.0
2. Run repomix with the `.ignore` file present
3. Check if `spec/data/openaip/de_apt.json` appears in the output
4. If it appears, the test fails and the issue is reproduced

## How to Check Results

Check the GitHub Actions workflow runs to see if the issue is reproduced. If the workflow fails with the message "ISSUE REPRODUCED", it confirms that `.ignore` file is not working properly in repomix v1.9.0.
