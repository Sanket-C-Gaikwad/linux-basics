## 1. What are Environment Variables?
When you login to a Linux system a shell environment gets setup for the user logging in. Bash environment variables defines the environment it creates when it launches. The information they carries and applies is your username, locale, history file size, your default editor, and a lot of other things. They too are defined by a key:value pair as shell variables.

```
- A variable can have more than one value and will be separated by a colon:
variable_name=value_1:value_2

---

- Quotation marks will be used if the variable has values with spaces in between:
variable_name="text value"

- List all env variable:
env
printenv

- If you know the variable name then just run the following command.
echo $variable_name

- You can either grep the variable and its value by running following command.
set | grep variable_name

- Setting non-persistent environment variables
export tutorial_name=env_variables

- Setting persistent environment variables. To set it for a single user, you need to edit the .bashrc file and add lines for each variable you wish to add in following format:
echo "export tutorial_name=env_variables" >> ~/.bashrc
echo $tutorial_name
logout
echo $tutorial_name


- Set it permanently for all the users: If you want to set it for all the users create an .sh file in the /etc/profile.d directory. Add your content, save and exit the file. The changes will be applied at the next logging in.
touch my_env_var.sh
echo "export tutorial_name=env_variables" >> my_env_var.sh
logout
echo $tutorial_name
sudo su - vagrant
echo $tutorial_name

- If you want to apply or make the environment active without logging out from the session run the following command.
source /etc/profile.d/my_env_var.sh
echo $tutorial_name

- Unset an Environment Variable: This will permanently remove the variables exported or set via a terminal command. The variables which are stored in configuration files (.bashrc or individual .sh files in etc/profiles.d directory) will also be removed from the current shell session. However, they will be set again once you login back next.
unset variable_name
```

