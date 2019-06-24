# Ensure Loan Fairness with AI Fairness 360

A machine learning model makes predictions of an outcome for a particular instance. (Given an instance of a loan application, predict if the applicant will repay the loan.) The model makes these predictions based on a training dataset, where many other instances (other loan applications) and actual outcomes (whether they repaid) are provided. Thus, a machine learning algorithm will attempt to find patterns, or generalizations, in the training dataset to use when a prediction for a new instance is needed. (For example, one pattern it might discover is "if a person has salary > USD 40K and has outstanding debt < USD 5, they will repay the loan".) In many domains this technique, called supervised machine learning, has worked very well.

However, sometimes the patterns that are found may not be desirable or may even be illegal. For example, a loan repay model may determine that age plays a significant role in the prediction of repayment because the training dataset happened to have better repayment for one age group than for another. This raises two problems: 1) the training dataset may not be representative of the true population of people of all age groups, and 2) even if it is representative, it is illegal to base any decision on a applicant's age, regardless of whether this is a good prediction based on historical data.

AI Fairness 360 is designed to help address this problem with fairness metrics and bias mitigators. Fairness metrics can be used to check for bias in machine learning workflows. Bias mitigators can be used to overcome bias in the workflow to produce a more fair outcome.

When the reader has completed this Code Pattern, they will understand how to:

* Compute a fairness metric on original data using [AI Fairness 360](https://github.com/IBM/AIF360)
* Mitigate bias by transforming the original dataset
* Compute fairness metric on transformed training dataset

## Flow

![architecture](doc/source/images/architecture.png)

1. User interacts with Watson Studio to create a Jupyter notebook
1. Notebook imports the AIF360 toolkit.
1. Data is loaded into the notebook.
1. User runs the notebook, which uses AIF360 tookit to assess fairness of Machine Learning model.

## Included components

* [Jupyter Notebook](https://jupyter.org/): An open source web application that allows you to create and share documents that contain live code, equations, visualizations, and explanatory text.
* [Tensorflow](https://www.tensorflow.org/): An open source software library for numerical computation using data flow graphs.
* [Watson Studio](https://www.ibm.com/cloud/watson-studio): Analyze data using RStudio, Jupyter, and Python in a configured, collaborative environment that includes IBM value-adds, such as managed Spark.
* [Python](https://www.python.org/): Python is a programming language that lets you work more quickly and integrate your systems more effectively.

## Steps

Either [run locally](#run-locally):

1. [Clone the repo](#1-clone-the-repo)
1. [Load the notebook](#2-load-the-notebook)

or [use Watson Studio](#use-watson-studio):

1. [Create a new project](#1-create-a-new-project)
1. [Create the notebook](#2-create-the-notebook)

then:

3. [Run the notebook](#3-run-the-notebook)

## Run locally

### 1. Clone the repo

Clone the repo locally. In a terminal, run:

```bash
git clone https://github.com/IBM/ensure-loan-fairness-aif360
```

### 2. Load the notebook

* Start your Jupyter Notebook process. Running in the `ensure-loan-fairness-aif360` cloned repo directory will help you find the notebook and the output as described below. The `jupyter notebook` process will open your browser.

   ```bash
   cd ensure-loan-fairness-aif360
   jupyter notebook
   ```

* Navigate to the `notebooks` directory and open the notebook file named `credit_scoring.ipynb`.

## Use Watson Studio

### 1. Create a new project

* Log into IBM's [Watson Studio](https://dataplatform.cloud.ibm.com). Once in, you'll land on the dashboard.

* Create a new project by clicking `+ New project` and choosing `Data Science`:

  ![studio project](https://raw.githubusercontent.com/IBM/pattern-utils/master/watson-studio/new-project-data-science.png)

* Enter a name for the project name and click `Create`.

* **NOTE**: By creating a project in Watson Studio a free tier `Object Storage` service and `Watson Machine Learning` service will be created in your IBM Cloud account. Select the `Free` storage type to avoid fees.

  ![studio-new-project](https://raw.githubusercontent.com/IBM/pattern-utils/master/watson-studio/new-project-data-science-name.png)

* Upon a successful project creation, you are taken to a dashboard view of your project. Take note of the `Assets` and `Settings` tabs, we'll be using them to associate our project with any external assets (datasets and notebooks) and any IBM cloud services.

  ![studio-project-dashboard](https://raw.githubusercontent.com/IBM/pattern-utils/master/watson-studio/overview-empty.png)

### 2. Create the notebook

* From the new project `Overview` panel, click `+ Add to project` on the top right and choose the `Notebook` asset type.

  ![studio-project-dashboard](https://raw.githubusercontent.com/IBM/pattern-utils/master/watson-studio/add-assets-notebook.png)

* Fill in the following information:

  * Select the `From URL` tab. [1]
  * Enter a `Name` for the notebook and optionally a description. [2]
  * Under `Notebook URL` provide the following url: [https://raw.githubusercontent.com/IBM/ensure-loan-fairness-aif360/master/notebooks/credit_scoring.ipynb](https://raw.githubusercontent.com/IBM/ensure-loan-fairness-aif360/master/notebooks/credit_scoring.ipynb) [3]
  * For `Runtime` select the `Python 3.5` option. [4]

  ![add notebook](https://github.com/IBM/pattern-utils/raw/master/watson-studio/notebook-create-url-py35.png)

* Click the `Create` button.

* **TIP:** Once successfully imported, the notebook should appear in the `Notebooks` section of the `Assets` tab.

### 3. Run the notebook

* Use the menu pull-down `Cell > Run All` to run the notebook, or run the cells one at a time top-down using the play button.

* As the cells run, watch the output for results or errors. A running cell will have a label like `In [*]`. A completed cell will have a run sequence number instead of the asterisk.

## Sample output

See [`examples/example_notebook.ipynb`](examples/example_notebook.ipynb):

![example output](doc/source/images/example_output.png)

## Links

* [AI Fairness 360 Toolkit (AIF360)](https://github.com/IBM/AIF360)
* [Live Demo of AI Fairness 360](https://aif360.mybluemix.net/data)
* [Contact AIF360 team on Slack](https://aif360.slack.com/)
* [IBM launches tools to detect AI fairness, bias and open sources some code](https://www.zdnet.com/article/ibm-launches-tools-to-detect-ai-fairness-bias-and-open-sources-some-code/)

## Learn more

* **Artificial Intelligence Code Patterns**: Enjoyed this Code Pattern? Check out our other [AI Code Patterns](https://developer.ibm.com/technologies/artificial-intelligence/).
* **Data Analytics Code Patterns**: Enjoyed this Code Pattern? Check out our other [Data Analytics Code Patterns](https://developer.ibm.com/technologies/data-science/)
* **AI and Data Code Pattern Playlist**: Bookmark our [playlist](https://www.youtube.com/playlist?list=PLzUbsvIyrNfknNewObx5N7uGZ5FKH0Fde) with all of our Code Pattern videos
* **Watson Studio**: Master the art of data science with IBM's [Watson Studio](https://www.ibm.com/cloud/watson-studio)

## License

This code pattern is licensed under the Apache Software License, Version 2. Separate third party code objects invoked within this code pattern are licensed by their respective providers pursuant to their own separate licenses. Contributions are subject to the [Developer Certificate of Origin, Version 1.1 (DCO)](https://developercertificate.org/) and the [Apache Software License, Version 2](https://www.apache.org/licenses/LICENSE-2.0.txt).

[Apache Software License (ASL) FAQ](https://www.apache.org/foundation/license-faq.html#WhatDoesItMEAN)
