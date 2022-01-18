[![GoKEV](http://GoKEV.com/GoKEV200.png)](http://GoKEV.com/)
<div style="position: absolute; top: 40px; left: 200px;">


# What is this?

This repo contains playbooks to manipulate ServiceNow tickets.
In order to utilize this and the certified Ansible collection,
you'll need an Ansible Automation Platform subscription as well
as a developer instance from ServiceNow.  Please don't run this
in production as-is.

* [Request a developer instance from ServiceNow directly](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/new_to_servicenow/app_store_learnv2_buildmyfirstapp_rome_personal_developer_instances "Request a developer instance from ServiceNow directly")

# vars used in create_ticket.yml
<pre>

# All fields below are optional, as a default value will be placed by this playbook where necessary.
---
# Can be low, medium, high -- (if omitted, these impact and urgency values default 'low' in this playbook).
- snticket_impact: low
- snticket_urgency: low
#Custom states can be added.  By default, this should be a string stating:  Pending, Open, Work in Progress, Closed Complete, Closed Incomplete, or Closed Skipped -- or "absent" to delete the incident
- snticket_state: Open
- snticket_caller:  The user who created the ticket.  This will default fo the service account running this playbook
- short_description: This is a short description of the issue.
- snticket_desc:  This is a description of the issue that goes into slightly more detail than the short description and probably has a lot more information that will be required for troubleshooting and root cause analysis.
- sn_slastart: 2022-01-18


</pre>

These examples differ slightly from the ones on the official documentation, because we are
using a custom credential and these playbooks don't need plaintext user / password / instance
written into them.  

<a href="https://github.com/ansible-collections/servicenow.itsm/blob/main/docs/servicenow.itsm.incident_module.rst" target="blank_window">The original documentation for this module is here.</a>

Examples:
--------

    - name: Create incident
        state: new
        caller: some.user
        short_description: User is not receiving email
        description: User has been unable to receive email for the past 15 minutes
        attachments:
          - path: path/to/attachment.txt
        impact: low
        urgency: low

        other:
          expected_start: 2021-02-12

    - name: Change state of the incident
      servicenow.itsm.incident:
        state: in_progress
        number: INC0000001

    - name: Close incident
      servicenow.itsm.incident:
        state: closed
        number: INC0000001
        close_code: "Solved (Permanently)"
        close_notes: "Closed"

    - name: Delete incident
      servicenow.itsm.incident:
        state: absent
        number: INC0000001










Author(s) Information
------------------
* Kevin Holmes :: kev@GoKEV.com

## Project origin and milestones:

This project was created in January 2022 by [Kevin Holmes](http://GoKEV.com/), based on the previous work of others.  Let's give them credit here:

- [Colin McCarthy's post on ServiceNow](https://www.ansible.com/blog/ansible-servicenow-opening-and-closing-tickets)
- [Michael Ford's post on ServiceNow APIs](https://www.ansible.com/blog/ansible-servicenow-howto-part-3-making-outbound-restful-api-calls-to-ansible-tower)
- [Some examples of using the Ansible Certified Collection from the Ansible blog](https://www.ansible.com/blog/certified-collection-servicenow)

## Become A Certified Red Hat Content Provider:

Please visit these links to learn more about certifying your content and partnering with Red Hat.  It's actually quite simple and great for recognition that your modules have gone the extra step to be recognized and supportable:

* [Red Hat Ansible Automation Platform Partners](https://www.ansible.com/partners "Red Hat Ansible Automation Platform Partners")
* [Ansible Certified Content FAQ](https://access.redhat.com/articles/4916901 "Ansible Certified Content FAQ")
* [Ansible Docs on Module Creation](https://docs.ansible.com/ansible/latest/dev_guide/developing_modules_general.html "Ansible Docs on Module Creation")

