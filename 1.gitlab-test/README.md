
Test connection btw gitlab and k8s with agent

Apply deployment
Add in /etc/hosts: Ingresss_ip  gitlab.local

Creare fake usr and pw:
Log into the remote machine: /opt/gitlab
Run: sudo gitlab-rails console

Create an usr and pw:

user = User.create!(
  email: 'nome.utente@example.com',
  username: 'nome_utente',
  name: 'Nome Cognome',
  password: 'password_segreta',
  password_confirmation: 'password_segreta'
)

user.admin = true!


exit


(dima,provaopenk9)

##################################
Create an agent configuration file
##################################

Choose a name for your agent. The agent name follows the DNS label standard from RFC 1123. The name must:

Be unique in the project.
Contain at most 63 characters.
Contain only lowercase alphanumeric characters or -.
Start with an alphanumeric character.
End with an alphanumeric character.
In the repository, in the default branch, create an agent configuration file at the root:

.gitlab/agents/<agent-name>/config.yaml