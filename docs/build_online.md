# Building Apps via Github Editor

Building Apps via the Github Editor allows you to build apps without having to install anything on  your local machine. It is considered simpler than buildng on your local machine and is perfectly suitable for those who aren't comfortable using basic git or python commands in a terminal window. 

Most of the instructions here are also part of the [Quickstart Guide](quickstart.md).

## Before you Begin

1. Before you continue, ensure that you have completed the **Pre-Requisites** and **Clone the Repository and Configure your Application** sections of the [Quickstart Guide](quickstart.md) and have the following

	* Your own forked version of <a href="https://github.com/jswope00/AI-MicroApp-Template" alt="Build AI Microapp" target="_blank">MicroApp template repository</a>

	* A github.com account

	* A streamlit.io account

	* An AI key (at least an OpenAI key)

## Customize or Build an App

1. Go to your forked GitHub repository.

2. It is generally easier to modify an existing app configuration rather than start from scratch. You can use the ```app_hello_world.py``` app as our simplest example. If you want to modify that app to write a sonnet about you and your favorite animal (the example from [Quickstart](quickstart.md)), you can replace all the content in that file with the following: 

		```python
		PHASES = {
		    "phase1": {
		        "name": "What is your name?",
		        "fields": {
		                "name": {
		                "type": "text_input",
		                "label": "What is your first name?",
		            },
		            "animal": {
		            	"type": "text_input",
		            	"label": "What is one of your favorite animals?"
		            }
		        },
		        "user_prompt": "My name is {name} and I like this animal: {animal}. Write a sonnet about me and my favorite animal.",
		    },
		}

		from core_logic.main import main
		if __name__ == "__main__":
		    main(config=globals())
		```

10. To get a better understanding of the configuration options you have when building apps, move on to the reference documentation. 

	* [Phases, Fields and Runs](concept_phases_fields_runs.md)
	* [Phases](reference_phases.md)
	* [Fields](reference_fields.md)
	* [Prompts](reference_prompts.md)

11. Click "Commit changes" to save the updated file. You'll be asked to add a commit message and confirm your commit. 
	
	![Commit Changes](img/commit_changes.png)


## Deploying to the Web

12. There are two ways to deploy to the web via Streamlit:

	* [Deploy a Single App](deploy.md#deploy-a-single-app) - Deploy a single app at a publicly accessible website. 

	* [Deploy your App Dashboard](deploy.md#deploy-an-apps-directory) - Deploy a gallery of all your published apps. 

