# discord-email-validation-bot

A project by Roman Ugarte and Mark Xu.

## overview

An automated validation process for verifying emails of a particular subdomain and assigning a given Discord role.

In this version, the bot verifies new joiners of a particular server and checks that they have an "@harvard.edu" email address. Once this is verified, they're given the role "Verified".

## file overview

There are three files:

**bot.py** is the main script for the bot. This is the one that is run. 

**send_email.py** is a helper script for sending emails via SendGrid's API. This is how the verification codes are sent.

**base.py** is a helper script for adding records to an Airtable database.

## set up

For the script to run on your local machine, you need to do the following:

**(1) Create and run a virtual environment.**

To create a virtual environment:

    python3 -m venv tutorial-env

To run it, on Unix or MacOS：

    source tutorial-env/bin/activate

And for Windows:

    tutorial-env\Scripts\activate.bat


**(2) Setting up SendGrid**

Storing a local API key (not for sharing publicly):

    echo "export SENDGRID_API_KEY='[hidden]'" > sendgrid.env
    echo "sendgrid.env" >> .gitignore
    source ./sendgrid.env
    pip install sendgrid

And downloading SendGrid:

    pip install sendgrid

**(3) Setting up Airtable**

Run the following in the terminal:

    pip3 install airtable-python-wrapper
    pip3 install requests

## initial functionality

When a user joins the Discord server, they use the command **/verify code**, which asks for their email address. If they input a non-Harvard email, they receive an error message.

Once they've submitted their email, they receive an automated email with a 9-digit verification code.

The next step is to use **/verify student** and input the same email as before, their verification code, and their full name. If the two email addresses and codes match, they're given the role "Verified". Their name and email addresses are also logged in an Airtable database.

To see how it works, [here](https://www.loom.com/share/918d979a87b34b44a74915633e9b154c)'s a short demo.

## future additions

There are a few improvements we plan to make:
* Deploy the script 24/7 on a cloud server.
* Extend functionality to alumni, not just students. Some manual process here.
* Customizability for other organizations (e.g., custom subdomains and Discord roles).
