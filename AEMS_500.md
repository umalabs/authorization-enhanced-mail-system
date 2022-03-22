<!-- @import "AEMS_500.less" -->

# Authorization-Enhanced Mail System in less than 500 words

<p class="author">
    Igor Zboran<br>
    izboran@gmail.com
</p>

## Concept

In this paper, the Correlated Authorization (AEMS) [1] mail trust framework—built on top of User-Managed Access (UMA) [2, 3] and OAuth 2.0 [4] protocols—is proposed to overcome the data storage, access control, and data transfer limitations of the current mail system. AEMS follows the concept of Correlated Authorization while keeping compatibility with the current mail system. We propose to integrate the Correlated Authorization framework with the mail system using a standardized SMTP/POP3/IMAP interface and at the same time mirror the existing email infrastructure by creating the parallel system of the email resource servers. A proprietary email application will be used to access the email resources, as illustrated in Figure 1. AEMS uses two-way push-pull data transfer mechanism—SMTP push and RESTful pull protocols.

![Authorization-Enhanced Mail System](./images/concept_500.svg)

<p class="figure">
Fig.&nbsp;1.&emsp;Concept
</p>

## Key points

1. An email consists of resources (message and attachments) stored in a RESTful Mailbox – an email-specific resource server.
2. The email resources owned by the sender stored in the sender’s RESTful Mailbox are temporarily shared with the recipient. Following a successful sharing process, an authorization email with the authorization code and the email resources identifier is sent to the recipient via the standard email system.
3. The recipient’s Mail Retrieval Agent that acts on behalf of the recipient retrieves the authorization email, gets delegated access using an authorization grant, and downloads the email resources from the sender’s RESTful Mailbox. The downloaded data are stored in the recipient's RESTful Mailbox.

## Advantages over Current Mail System

1. Security and Privacy: User correspondence takes place between RESTful Mailboxes. The mailbox of the current email system is only used for system (registration, notification) emails. This architecture guarantees more control over potential security and privacy issues such as leakage of intellectual property or loss of confidential content and makes the system compatible with enterprise security policies.
2. Usability: The RESTful Mailbox is decoupled from the email address. This allows a user with a single email address to use simultaneously multiple RESTful Mailboxes. To separate official, business, personal and healthcare correspondence, AEMS provides the flexibility for storing emails according to various criteria within an appropriate RESTful Mailbox provider. 
3. Platform: With the capability to store, locate, send and receive any content including documents, images, audios and videos, the proposed solution can be considered a promising platform for Content Services.

## References

<p class="references">
[1]&nbsp;I. Zboran “Correlated Authorization” GitHub repository https://github.com/umalabs/correlated-authorization/raw/main/Correlated_Authorization.pdf.<br>
[2]&nbsp;E. Maler, M. Machulak, J. Richer, and T. Hardjono, “User-Managed Access (UMA) 2.0 Grant for OAuth 2.0 Authorization,” Internet Engineering Task Force (2019), https://docs.kantarainitiative.org/uma/wg/rec-oauth-uma-grant-2.0.html.<br>
[3]&nbsp;E. Maler, M. Machulak, J. Richer, and T. Hardjono, “Federated Authorization for User-Managed Access (UMA) 2.0” Internet Engineering Task Force (2019), https://docs.kantarainitiative.org/uma/wg/rec-oauth-uma-federated-authz-2.0.html.<br>
[4]&nbsp;E. D. Hardt, “The OAuth 2.0 Authorization Framework,” IETF RFC 6749 (Informational), 2012, http://tools.ietf.org/html/rfc6749.<br>
</p>