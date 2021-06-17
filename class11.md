# OAuth 

> What is OAuth ?

*OAuth is an open-standard authorization protocol or framework that describes how unrelated servers and services can safely allow authenticated access to their assets without actually sharing the initial, related, single logon credential.* 

> Give an example of what using OAuth would look like.

*OAuth scenario could be a user sending cloud-stored files to another user via email, when the cloud storage and email systems are otherwise unrelated other than supporting the OAuth framework (e.g., Google Gmail and Microsoft OneDrive). When the end-user attaches the files to their email and browses to select the files to attach, OAuth could be used behind the scenes to allow the email system to seamlessly authenticate and browse to the protected files without requiring a second logon to the file storage system.* 

> How does OAuth work? What are the steps that it takes to authenticate the user ? 

*Let’s assume a user has already signed into one website or service (OAuth only works using HTTPS). The user then initiates a feature/transaction that needs to access another unrelated site or service.* 

* The first website connects to the second website on behalf of the user, using OAuth, providing the user’s verified identity. 

* The second site generates a one-time token and a one-time secret unique to the transaction and parties involved. 

* The first site gives this token and secret to the initiating user’s client software. 

* The client’s software presents the request token and secret to their authorization provider. 

* If not already authenticated to the authorization provider, the client may be asked to authenticate. After authentication, the client is asked to approve the authorization transaction to the second website. 

* The user approves a particular transaction type at the first website. 

* The user is given an approved access token. 

* The user gives the approved access token to the first website. 

* The first website gives the access token to the second website as proof of authentication on behalf of the user.

* The second website lets the first website access their site on behalf of the user.

* The user sees a successfully completed transaction occurring.

* OAuth is not the first authentication/authorization system to work this way on behalf of the end-user. 

> What is OpenID ? 

*OpenID is about authentication: as a commenter on StackOverflow pithily put it: "OpenID is for humans logging into machines, OAuth is for machines logging into machines on behalf of humans."* 

# Authorization and Authentication flows 

> What is the difference between authorization and authentication ? 

| Authentication | Authorization | 
|----------------|---------------| 
| Determines whether users are who they claim to be | Determines what users can and cannot access | 
| Challenges the user to validate credentials | Verifies whether access is allowed through policies and rules | 
| Usually done before authorization | Usually done after successful authentication | 
| Generally, transmits info through an ID Token | Generally, transmits info through an Access Token | 
| Generally governed by the OpenID Connect (OIDC) protocol | Generally governed by the OAuth 2.0 framework | 
| Example: Employees in a company are required to authenticate through the network before accessing their company email | Example: After an employee successfully authenticates, the system determines what information the employees are allowed to access | 

> What is Authorization Code Flow ? 

*Because regular web apps are server-side apps where the source code is not publicly exposed, they can use the Authorization Code Flow (defined in OAuth 2.0 RFC 6749, section 4.1), which exchanges an Authorization Code for a token. Your app must be server-side because during this exchange, you must also pass along your application's Client Secret, which must always be kept secure, and you will have to store it in your client.* 

> What is Authorization Code Flow with Proof Key for Code Exchange (PKCE) ? 

*When public clients request Access Tokens, some additional security concerns are posed that are not mitigated by the Authorization Code Flow alone.* 

* Native apps 

1. Cannot securely store a Client Secret. 
2. May make use of a custom URL scheme to capture redirects  potentially allowing malicious applications to receive an Authorization Code from your Authorization Server. 

* Single-page apps 

1. Cannot securely store a Client Secret because their entire source is available to the browser. 

> What is Implicit Flow with Form Post ?

*As an alternative to the Authorization Code Flow, OAuth 2.0 provides the Implicit Flow, which is intended for Public Clients, or applications which are unable to securely store Client Secrets.* 

> What is Client Credentials Flow ? 

*With machine-to-machine (M2M) applications, such as CLIs, daemons, or services running on your back-end, the system authenticates and authorizes the app rather than a user. For this scenario, typical authentication schemes like username + password or social logins don't make sense. Instead, M2M apps use the Client Credentials Flow.* 

> What is Device Authorization Flow ? 

*With input-constrained devices that connect to the internet, rather than authenticate the user directly, the device asks the user to go to a link on their computer or smartphone and authorize the device. This avoids a poor user experience for devices that do not have an easy way to enter text. To do this, device apps use the Device Authorization Flow. For use with mobile/native applications.* 

> What is Resource Owner Password Flow ?

*highly-trusted applications can use the Resource Owner Password Flow, which requests that users provide credentials (username and password), typically using an interactive form. The Resource Owner Password Flow should only be used when redirect-based flows cannot be used.* 
