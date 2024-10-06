# Building Apps from your Local Computer

A local deployment allows you to use your own text or code editor and test your apps locally before pushing them to the web. If you aren't comfortable using a terminal window and some basic git and python commands, then you can continue [Building Apps using the Github Editor](build_online.md).


## Pre-Requisites

1. You should have a forked version of the <a href="https://github.com/jswope00/AI-MicroApp-Template" alt="Build AI Microapp" target="_blank">MicroApp template repository</a>. Follow the instructions in the [Quickstart](quickstart.md). 

2. You need to have Git, Python and Pip installed on your machine, and a basic understanding of how to use them. 


## Clone the Repository and Configure your Application

1. In your terminal window, navigate to a directory where you want to keep your MicroApps and clone your forked repository:

		git clone https://github.com/[Github User Name]/AI-MicroApps.git

2. Navigate into the newly created directory. 

		cd AI-MicroApps

3. Create a virtual environment
		
		python3 -m venv venv

4. Activate your virtual environment.

		source venv/bin/activate

	> **Note:** You should activate your virtual environment any time you are running or working in your AI-MicroApps directory.

5. With your virtual environment activated, install the requirements. 

		pip3 install -r requirements.txt

6. Create a ```.env``` file in the root directory and paste the following:

		OPENAI_API_KEY="[My OpenAI Key]"
		GOOGLE_API_KEY="[My Google Gemini Key]"
		CLAUDE_API_KEY="[My Claude Key]"
		PERPLEXITY_API_KEY="[My Perplexity Key]"

	> **Note:** You can leave placeholders for any keys you don't have or don't want to use. You should at least add the OpenAI key, since the template defaults to OpenAI. 

## Run Your Apps

7. You can run either a single app or the App Directory to see all Published Apps. 

	To run a **single app**:

		streamlit run [app config file]


	e.g. ```streamlit run app_hello_world.py```

	To run the **App Directory** and view all files: 

		streamlit run apps_directory.py

8. An app window should launch at ```localhost:8501```

## Customize or Build an App

9. It is generally easier to modify an existing app configuration rather than start from scratch. You can use the ```app_hello_world.py``` app as our simplest example. If you want to modify that app to write a sonnet about you and your favorite animal (the example from [Quickstart](quickstart.md)), you can replace all the content in that file with the following: 

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

10. To get a better understanding of the configuration options you have when building apps, move on to the reference documentation. 

	* [Phases, Fields and Runs](concept_phases_fields_runs.md)
	* [Phases](reference_phases.md)
	* [Fields](reference_fields.md)
	* [Prompts](reference_prompts.md)

11. Most changes are reflected once you save your app configuration file. Occasionally, changes might require that you restart the Streamlit server. 

	To stop your streamlit server, navigate to terminal where your app is running and type ```Ctrl + C```

	To start your streamlit server, the command is either ```streamlit run [app config file]``` for a single app or ```streamlit run apps_directory.py``` for the Apps Directory

## Commit your Changes

12. When you are ready to deploy your changes to the web, you must commit them to the Git repository first. The commands might look like this: 

	```git add . ``` To add all your files to a git commit.

	```git commit -m "[My Commit Message]"``` to add a descriptive message about what you are committing. 

	```git push origin main``` to push your changes to your remote repository. 

	Use <a href="https://docs.github.com/en" alt="Github Docs" target="_blank">Github's official documentation</a> or an AI service like ChatGPT for any questions about how to commit your changes to your remote repository. 

## Deploy to the Web

12. There are two ways to deploy to the web via Streamlit:

	* [Deploy a Single App](deploy.md#deploy-a-single-app) - Deploy a single app at a publicly accessible website. 

	* [Deploy your App Dashboard](deploy.md#deploy-an-apps-directory) - Deploy a gallery of all your published apps. 

