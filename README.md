# My-Custom-NU-Templates 

My cutom sensitive config files disclosure template

- With extra filtering to reduce false positives by checking for likely config keywords (API keys, secrets, DB credentials, etc.

## Improvements:

- Keyword filtering to avoid false positives (only alerts if likely sensitive terms are found).

- Content-type check so HTML 200 responses from error pages aren’t matched.

- All paths from your list covered in one template.

- v3 syntax and clean formatting.

Author: ChatGPT and Prompt by Me : )

## The Prompt i used :-  


By learning from this :- id: django-debug info: name: Django Debug Exposure author: wadgamer10 severity: low description: Detects Django Debug Toolbar or leaked config files tags: django,debug,dev http: - method: GET path: - "{{BaseURL}}/__debug__/" - "{{BaseURL}}/config" - "{{BaseURL}}/settings.py" matchers-condition: and matchers: - type: status status: - 200 - type: word words: - "Django Debug Toolbar" - "INTERNAL_IPS" - "ALLOWED_HOSTS" - "DEBUG = True" condition: or - type: word part: header words: - "text/html" - "text/x-python" 

Create a v3 nuclei template that checks for sensitive files disclosure according to this wordlist :-

app/config.js, app/config.json, config.js, config.json, app/config, app/configuration, app/env.js, app/env.json, server.js, server.json, configuration.js, configuration.json, app/server.js, app/server.json 

and make it clean from false positive results

