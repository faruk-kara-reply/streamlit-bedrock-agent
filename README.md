# Agents for Amazon Bedrock Test UI

A generic Streamlit UI for testing generative AI agents built using Agents for Amazon Bedrock. For more information, refer to the blog post [Developing a Generic Streamlit UI to Test Amazon Bedrock Agents](https://blog.avangards.io/developing-a-generic-streamlit-ui-to-test-amazon-bedrock-agents).

# Prequisites

- [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
- [Python 3](https://www.python.org/downloads/)

# Running Locally

1. Run the following `pip` command to install the dependencies:

   ```
   pip install -r requirements.txt
   ```

2. Configure your AWS CLI with credentials that have permissions to invoke the Bedrock agent:
   ```
   aws configure
   ```
3. Set the following environment variables either directly in `services/bedrock_agent_runtime.py` or using a `.env` file (use `.env.template` as a starting point):
   - `BEDROCK_AGENT_ID` - The ID of the agent.
   - `BEDROCK_AGENT_ALIAS_ID` - The ID of the agent alias. The default `TSTALIASID` will be used if it is not set.
   - The [AWS environment variables](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html) that provides the credentials to your account. The principal must have the necessary permissions to invoke the Bedrock agent.
4. (Optional) Set the following environment variables similarly to customize the UI:
   - `BEDROCK_AGENT_TEST_UI_TITLE` - The page title. The default `Agents for Amazon Bedrock Test UI` will used if it is not set.
   - `BEDROCK_AGENT_TEST_UI_ICON` - The favicon, such as `:bar_chart:`. The default Streamlit icon will be used if it is not set.
5. (Optional) Set the `LOG_LEVEL` environment variable for additional logging using a standard format. If more advanced configuration is needed, copy `logging.yaml.template` and `logging.yaml` and configure it as appropriate.
6. Run the following command to start the Streamlit app:

   ```
   streamlit run app.py --server.port=8080 --server.address=localhost
   ```
