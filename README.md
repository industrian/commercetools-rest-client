# commercetools-rest-client

This repository contains .http files which you can use to interact with commercetools Composable Commerce APIs using the REST Client extension for Visual Studio Code.

# Disclaimer

- This repository and its contents are not provided by or supported by commercetools.
- The .http files and their API calls are intended for testing/evaluation purposes only and should not be used in production.
- The .http files and their contents are accurate as of the time their files were last updated.

You should consult the [commercetools documentation](https://docs.commercetools.com/api/) for more information regarding required fields and data types in each API call.

# Requirements

- A commercetools Composable Commerce Project ([sign up](https://docs.commercetools.com/getting-started/initial-setup))
- [An API Client](https://docs.commercetools.com/getting-started/create-api-client)

# Set up

1. Open your Visual Studio Code User Settings (JSON) file.
2. Find `rest-client.environmentVariables` and add an object with your Project key as the name. This will set up an environment for the Project. The following fields must be added: 
    - `project-key`: the Project key
    - `client_secret`: your API Client secret
    - `client_id`: your API Client id
    - `auth_url`: the authorization URL of the region your Project is hosted
    - `host`: the API URL of the region your Project is hosted
    - `scopes`: your API Client scopes

For example:


You can define multiple Projects within the settings file. These Projects can then be switched by clicking the Switch REST Client Environment button.

# Making API calls

Each API call is within a dedicated .http file, nested under folders representing the resource. Update actions are also within a dedicated folder.

At the beginning of every file is an Authentication call. You must make ths call first. It will get and save the bearer token.

Variables used within API calls are defined above the call. You should define these before sending the API request. For example, in the following you must add a `category-id` and `category-version`. Strings should not be enclosed in quotation marks.

In some API calls you can define query parameters (such as `where` or `sort`). Placeholders for these parameters are included, but commented out. To define a query parameter, remove the `#` and include a value. Please note that you should change the `&` to `?` if it is the first (or only) query parameter.