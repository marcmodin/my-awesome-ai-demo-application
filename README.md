# My-awesome-ai-demo-application-service
"This is a python demo application using Langserve and running in Kubernetes "

## Installation

Install Poetry and the LangChain CLI if you haven't yet

```bash
pip install -U langchain-cli poetry
```

Its a good idea to start a virtual environment before installing any thing

```
poetry shell & poetry install --all-extras
```

## Adding Langserve Packages

```bash
# adding packages from 
# https://github.com/langchain-ai/langchain/tree/master/templates
langchain app add $PROJECT_NAME

# adding custom GitHub repo packages
langchain app add --repo $OWNER/$REPO
# or with whole git string (supports other git providers):
# langchain app add git+https://github.com/hwchase17/chain-of-verification

# with a custom api mount point (defaults to `/{package_name}`)
langchain app add $PROJECT_NAME --api_path=/my/custom/path/rag
```

Note: you remove packages by their api path

```bash
langchain app remove my/custom/path/rag
```

## Setup LangSmith (Optional)
LangSmith will help us trace, monitor and debug LangChain applications. 
LangSmith is currently in private beta, you can sign up [here](https://smith.langchain.com/). 
If you don't have access, you can skip this section


```shell
export LANGCHAIN_TRACING_V2=true
export LANGCHAIN_API_KEY=<your-api-key>
export LANGCHAIN_PROJECT=<your-project>  # if not specified, defaults to "default"
```

## Launch LangServe Locally

Make sure you are authenticated to AWS and have exported `AWS_DEFAULT_REGION` in the terminal

```bash
langchain serve
```
