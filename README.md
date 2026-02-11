# GitHubActionLab-ArturSharipov
In-class activity to practice GitHub actions 
Purpose

This workflow demonstrates how to run independent jobs in parallel across multiple operating systems.

What it does
	•	The workflow triggers on pull requests to the main branch
	•	It runs three independent jobs simultaneously:
	•	Ubuntu job (Linux)
	•	Windows job
	•	macOS job
	•	Each job:
	•	Checks out the repository code
	•	Displays operating system information
	•	Executes an OS-specific command
	•	Creates a file and prints its contents

This shows how GitHub Actions can test software in different environments at the same time.


Key Concepts Demonstrated

needs

The needs keyword is used in Workflow 1 to define job dependencies. It ensures jobs run in a specific order:
	•	test needs build
	•	deploy needs test

This creates a controlled pipeline where later stages wait for earlier stages to finish successfully.

runs-on

The runs-on property specifies the operating system used for each job. Examples include:
	•	ubuntu-latest
	•	windows-latest
	•	macos-latest

This allows workflows to run on different platforms and ensures compatibility across environments.


env

Environment variables can be used to share configuration or system information between steps. In these workflows, environment data such as the runner OS is printed to show how jobs access system information.


Challenges and Solutions

Challenge 1: Understanding job dependencies

It was initially unclear how to enforce execution order between jobs. This was resolved by learning how the needs keyword creates explicit dependencies between jobs.

Challenge 2: Running OS-specific commands

Different operating systems require different commands. For example:
	•	Linux/macOS use uname -a
	•	Windows uses PowerShell commands like systeminfo

This was solved by using OS-appropriate commands and specifying the correct shell where needed.

Challenge 3: Verifying parallel execution

To confirm that jobs were running simultaneously in Workflow 2, the GitHub Actions visualization graph was used to observe parallel execution in real time.


Conclusion

This project demonstrates how GitHub Actions can automate workflows with both sequential pipelines and parallel multi-platform testing. It highlights essential CI/CD concepts such as job dependencies, environment configuration, and cross-platform execution.
