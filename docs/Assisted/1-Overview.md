# Overview

The Finch Assisted API enables access to 70+ more providers in the Finch standard API format with our internal and on-shore Product Operations team. We want Finch to be the single infrastructure layer to access payroll and HR providers and this product allows us to enable maximum coverage.


## Enablement

To enable Assisted API, please email [developers@tryfinch.com](mailto:developers@tryfinch.com).


## How it works

The Assisted API uses a system supported by all payroll and HR systems, the addition of Third-Party Admins or Third-Party Accountants.

### Employer
1. Employer lands on the Connect `select` page.
2. Employer chooses a payroll provider Finch don't support via an API connection.
3. Instead of showing the credential login page, we display a page with the instructions to allow `<application_name>` to be added as an admin user to their payroll account.
4. The employer will provide a contact email address.
5. The employer clicks on confirm and proceeds with the application's normal flow.


### Application

1. The developer registers a custom domain (`payroll@acme.com`) and enables forwarding to a Finch email.
2. The `assisted` flag is enabled on Connect, and thereby showing all additional providers supported by the Assisted API.
3. Once the employer has approved the admin access, the application will retrieve an `auth_code`. The application will then exchange it for an `access_token` following the standard [Authorization]() flow.
4. The `access_token` will be returned with the assisted flag. Request can be made using the assisted `access_token` to the same endpoints. 
5. An application requests certain data points and Finch will return an HTTP status code 202 with an empty body indicating that the token is for Assisted connection requests and we have queued up the request for our Product Operations team.
6. The application polls the `GET /employer/{endpoint}/assisted/{job_id}` to check the status of the job and fulfilled data.

