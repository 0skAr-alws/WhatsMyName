# WhatsMyName
This repository has the unified data required to perform user enumeration on various websites. Content is in a JSON file and can easily be used in other projects.

# Format
The format of the JSON is simple. There are 3 main elements:

1. License - The license for this project and its data
2. Authors - The people that have contributed to this project
3. Sites - This is the main data

Within the "sites" elements, the format is as follows:

```json
     ...
      {
         "name" : "name of the site",
         "check_uri" : "URI to check the site with the {account} string replaced by a username",
         "pretty_uri" : "if the check_uri is for an API, this OPTIONAL element can show a human-readable page",
         "account_existence_code" : "the HTTP response code for a good 'account is there' response",
         "account_existence_string" : "the string in the response that we look for for a good response",
         "account_missing_string" : "this OPTIONAL string will only be in the response if there is no account found ",
         "account_missing_code" : "the HTTP response code for a bad 'account is not there' response",
         "known_accounts" : ["a list of user accounts that can be used to test","for user enumeration"],
         "allowed_types" : ["these are the types of data and categories of the content"],
         "category" : "a category for what the site is mainly used for",
         "valid" : "this true or false boolean field is used to enable or disable this site element",
         "comments" : ["a list of comments including when this was last verified and outcomes"]
      },
      ...
```

Here is an example of a site element:

```json
     ...
      {
         "name" : "GitHub",
         "check_uri" : "https://api.github.com/users/{account}",
         "pretty_uri" : "https://github.com/{account}",
         "account_existence_code" : "200",
         "account_existence_string" : "login:",
         "account_missing_string" : ["Not Found"],
         "account_missing_code" : "404",
         "known_accounts" : ["test"],
         "allowed_types" : ["String","Person","WebAccount","Username","Organization"],
         "category" : "coding",
         "valid" : true,
         "comments" : ["verified 11/08/2015 - webbreacher"]
      },
      ...
```


# Contributors
@webbreacher<br>
@mmaczko
