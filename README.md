## livechatR - LiveChat REST API client for R


The package livechatR provides an interface from R to LiveChat's API endpoints
(see https://developers.livechatinc.com/rest-api/).

This package contains functions that curl the most frequently used API endpoints (agents, canned responses ahd chats).

### Features

- Authentication by constructing the necessary request URL using the LiveChat's API key and Email.
- Easy parameterization and result parsing for the following API requests:
  - `agents/`: get the list of agents using `livechatGetAgents`.
  - `canned_responses/`: get the list of canned responses using `livechatGetCannedResponses`.
  - `goals/`: get the list of goals using `livechatGetGoals`.
  - `greetings/`: get the list of greetings using `livechatGetGreetings`.
  - `chats/`: get the list of chat sessions, raw chat text and events using `livechatGetChats`.

### Installation

``` r
require(devtools)
devtools::install_github("lawwu/livechatR")
require(livechatR)
```


### Dependencies

The package depends on
- dplyr
- purrr
- jsonlite
- data.table
- magrittr

### Examples

#### Set-up connection using LiveChat credentials in R

In order to use the various methods of this package, we need to save the account data of your LiveChat email and API key into a named object using `livechatCreateAccount`. The next examples all make use of this account object. You can find the API Key and token [here](https://my.livechatinc.com/agents/api-key).

``` r
## Fill in here the API token, key and secret as found on
## https://my.livechatinc.com/agents/api-key
> account = livechatCreateAccount(email ="email_here",
                                  api_key = "api_key_here")
```

#### List Agents

``` r
> livechatGetAgents(account)
...
```

#### List Canned Responses

``` r
> livechatGetCannedResponses(account, group = 0)
```

#### List Chat Sessions and Chats

``` r
> livechat_data <- livechatGetChats(account, date_from = "2016-02-23")
```


