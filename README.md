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
---
- snticket_state: 
- snticket_caller:
- short_description: playbook created missing short description
- snticket_desc:
</pre>












## Become A Certified Red Hat Content Provider:

Please visit these links to learn more about certifying your content and partnering with Red Hat.  It's actually quite simple and great for recognition that your modules have gone the extra step to be recognized and supportable:

* [Red Hat Ansible Automation Platform Partners](https://www.ansible.com/partners "Red Hat Ansible Automation Platform Partners")
* [Ansible Certified Content FAQ](https://access.redhat.com/articles/4916901 "Ansible Certified Content FAQ")
* [Ansible Docs on Module Creation](https://docs.ansible.com/ansible/latest/dev_guide/developing_modules_general.html "Ansible Docs on Module Creation")


Author(s) Information
------------------
* Kevin Holmes :: kev@GoKEV.com

## Project origin and milestones:

This project was created in January 2022 by [Kevin Holmes](http://GoKEV.com/), based on the previous work of others.  Let's give them credit here:

- [Colin McCarthy's post on ServiceNow](https://www.ansible.com/blog/ansible-servicenow-opening-and-closing-tickets)
- [Michael Ford's post on ServiceNow APIs](https://www.ansible.com/blog/ansible-servicenow-howto-part-3-making-outbound-restful-api-calls-to-ansible-tower)
- [Some examples of using the Ansible Certified Collection from the Ansible blog](https://www.ansible.com/blog/certified-collection-servicenow)

