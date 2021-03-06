# Introduction

Welcome to Finch! Below you'll find everything you need to get started with Finch. If you have any questions, please email us [developers@tryfinch.com](mailto:developers@tryfinch.com)!

Finch makes it easy to read workforce data and push changes across providers (payroll, HRIS, time management, etc) using HTTP requests. We use built-in HTTP features like HTTP verbs and HTTP authentication so you can use any HTTP client. All responses are returned in standard JSON and are documented here.

All requests made to our API require an access token. Our API provides a granular permissioning system that authorizes individual products based on end-user consent. Applications can quickly authorize and interact with payroll providers through the Finch API

***

## Registration

To get started, register your application with Finch by emailing [developers@tryfinch.com](mailto:developers@tryfinch.com).

After registration, your application will be assigned a client ID and a client secret. The client secret must be kept safe and used only in exchanges between your application's server and Finch's server (`https://api.tryfinch.com`).
