# [automation-setup](https://github.com/nguyentrieuanduong/automation-setup.git)

**Automation Setup Environment**

# Installation

1. Create python virtual environment

   ```shell
   python3 -m venv venv
   ```

2. Activate the created python virtual environment

   ```shell
   source venv/bin/activate
   ```

3. Upgrade pip, setuptools and wheel

   ```shell
   pip install --upgrade pip setuptools wheel
   ```

4. Installing

   ```shell
   pip install -r requirements.txt
   ```

   Or [install ansible manually](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#pip-install)

   ```shell
   pip install ansible
   ```

   and [install ansible-lint manually](https://ansible-lint.readthedocs.io/installing/#installing-the-latest-version)

   ```shell
   pip install ansible-lint
   ```

5. Confirming your installation

   ```shell
   ansible --version
   pip show ansible
   ```

6. Adding Ansible command shell completion

   ```shell
   pip install argcomplete
   ```

7. Configure argcomplete to allow shell completion of the Ansible command line utilities

   ```shell
   eval $(register-python-argcomplete ansible)
   eval $(register-python-argcomplete ansible-config)
   eval $(register-python-argcomplete ansible-console)
   eval $(register-python-argcomplete ansible-doc)
   eval $(register-python-argcomplete ansible-galaxy)
   eval $(register-python-argcomplete ansible-inventory)
   eval $(register-python-argcomplete ansible-playbook)
   eval $(register-python-argcomplete ansible-pull)
   eval $(register-python-argcomplete ansible-vault)
   ```

8. Initiate [config file](https://docs.ansible.com/ansible/latest/cli/ansible-config.html)
   with [default example](https://docs.ansible.com/ansible/latest/reference_appendices/config.html#generating-a-sample-ansible-cfg-file)

   ```shell
   ansible-config init --disabled -t all -f ini > ansible.cfg
   ```

9. Check config file

   ```shell
   ansible-config --version
   ansible --version
   ```

10. [Ansible Galaxy](https://galaxy.ansible.com/): [Install multiple collections with a requirements file](https://docs.ansible.com/ansible/latest/galaxy/user_guide.html#install-multiple-collections-with-a-requirements-file) ([List of collections](https://docs.ansible.com/ansible/latest/collections/index.html#list-of-collections))

    ```shell
    ansible-galaxy install -r requirements.yml #--force
    ```

    Or [installing a collection from Galaxy](https://docs.ansible.com/ansible/latest/galaxy/user_guide.html#installing-a-collection-from-galaxy)

    ```shell
    ansible-galaxy collection install community.general --upgrade
    ```

11. Test ansible galaxy

    ```shell
    ansible-galaxy collection list
    ansible-galaxy role list
    ```

12. Test ansible

    ```shell
    ansible localhost -m ping
    echo "exit" | ansible-console localhost
    ```

# Usage

1. Verify the playbook

   ```shell
   ansible-lint hello-world-playbook.yml
   ```

2. Run ansible playbook

   ```shell
   ansible-playbook hello-world-playbook.yml
   ```

3. [Creating Roles](https://galaxy.ansible.com/docs/contributing/creating_role.html)

   ```shell
   ansible-galaxy role init --init-path roles hello-world
   ```
