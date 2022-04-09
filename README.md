# discord-validation-bot

A project by Roman Ugarte and Mark Xu.

## overview

An automated validation process for verifying emails of a particular subdomain and assigning a Discord role.

## v1

The following basic flow:
* Bot sends individualized, private welcome messages to new joiners of the Harvard Blockchain server.
* Bot asks for a valid "harvard.edu" email address, user responds.
* Bot sends an email to the provided email address with an eight-digit confirmation code.
* User sends confirmation code in Discord.
* If code matches, user is given the "Harvard" Discord role.

## v2
Additional features to be added:
* Store user information (name, Discord username, email) in a database.
* Add verified emails to the club's Google Group.
* Similar (semi-manual) filtering flow for "Alum" and "Fren" roles.
* Customizability for other organizations (e.g., custom subdomains and Discord roles).
