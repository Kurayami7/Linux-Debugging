# Linux-Debugging
A repository intended to guide Linux enthusiasts to resolve uncommon issues and errors.

## Issue 1: User is not in the sudoers file. This incident will be reported

If you see a message like “user is not in the sudoers file. This incident will be reported”, it means your user doesn’t have `sudo` privileges.

To solve this, you need to have access to an account that does have `sudo` privileges (often the `root` account), and use it to add your user to the `sudoers` file. Here’s how you can do it:

1. **Log in or switch to the account with `sudo` privileges**: You can switch accounts using the `su` command followed by the username. For example, to switch to the `root` account, you would use `su root`.

2. **Add your user to the `sudoers` file**: Once you’re logged in with an account that has `sudo` privileges, you can add your user to the `sudoers` file. The safest way to edit the `sudoers` file is using the `visudo` command, which opens the file in a text editor and checks for errors when you save and quit.

3. **Give your user `sudo` privileges**: In the `sudoers` file, you can add a line to give your user `sudo` privileges. The line should look like this: `<your-username> ALL=(ALL:ALL) ALL`. This line means that your user can run any command with `sudo` on any host.

4. **Save the file and exit the editor**: If you’re using `visudo`, you can save and quit by pressing `Ctrl+X`, then `Y` to confirm saving, and then `Enter` to confirm the file name.

5. **Log out and log back in with your user account**: You should now be able to use `sudo`.
