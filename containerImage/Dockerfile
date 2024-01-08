FROM python:3.8.16

#Install gcc because we will need it to build some of the
#python dependencies
RUN apt-get update && apt-get install -y gcc
#Update pip (pythons package manager)
RUN python -m pip install --upgrade pip && pip install virtualenv

#Copy in our model
COPY HAR_MulticlassDecisionForest_IE /HAR_MulticlassDecisionForest_IE

#Install the model requirements
RUN pip install -r HAR_MulticlassDecisionForest_IE/requirements.txt

#Tell it how to run the model
CMD ["mlflow", "models", "serve", "-h", "0.0.0.0", "-m", "irisPractical_", "--env-manager=local"]


