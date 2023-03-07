# devRelDays-CICD
Sample code for the Developer Relation days demo on automated IIQ builds.

## How To Use

* In the folder `ansible/roles/identityiq/files/` , place your IIQ installation files (identityiq.zip and all wanted patch jars)
* Create a file `ansible/vault-password-file`, and add the password to use to encrypt any secrets with ansible vault.

```bash
ansible-vault edit ansible/roles/identityiq/vars/secrets.yaml --vault-password-file ansible/vault-password-file
```

* Put the following variables in there: 
```
iiq_admin_password: replace_with_adminpassword
git_user: replace_with_gitusername
git_pat: replace_with_gitPAT
```

* In the Vagrantfile (`vagrant/Vagrantfile`), refer to the correct vagrant box with the `config.vm.box` parameter. Example: 
```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "debian/bullseye64"
end
```
* In the file `ansible/roles/identityiq/defaults/main.yml`, set the correct versions of the GA and patch version for IIQ you want to deploy.
* In the same file, set the variables `repo_url` and `repo_name` to refer to your repository of your IIQ artefacts.
* Run
```bash
cd vagrant
vagrant up
```
* Browse to http://localhost:8181/identityiq

## How to re-use

* `vagrant halt` to stop the VM
* `vagrant up` to start it again, in the halted condition.
* `vagrant provision` to force the provisioning step again
* `vagrant destroy` to start over (run `vagrant up` again)