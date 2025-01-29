# [Setup SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

## 1. Generating a new SSH key

1. Open Terminal.
2. Paste the text below, replacing the email used in the example with your GitHub email address. \
   `ssh-keygen -t ed25519 -C "your_email@example.com"`

> Note \
> If you are using a legacy system that doesn't support the Ed25519 algorithm, use: \
> `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

## 2. Adding your SSH key to the ssh-agent

1. Start the ssh-agent in the background. \
   `eval "$(ssh-agent -s)"`
2. Add your SSH private key to the ssh-agent. \
   `ssh-add ~/.ssh/id_ed25519`
3. Verify the SSH key is added to the ssh-agent. \
   `ssh-add -l`

## [3. Adding a new SSH key to your GitHub account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

1. Copy the SSH public key to your clipboard. \
   `cat ~/.ssh/id_ed25519.pub`
2. Go to GitHub and sign in.
3. In the upper-right corner of any page, click your profile photo, then click **Settings**.
4. In the user settings sidebar, click **SSH and GPG keys**.
5. Click **New SSH key** or **Add SSH key**.
6. In the **Title** field, add a descriptive label for the new key.
7. Paste your key into the **Key** field.
8. Click **Add SSH key**.
9. If prompted, confirm your GitHub password.
10. Confirm the action by clicking **Add SSH key**.
11. Verify the new SSH key is added to your GitHub account.
12. Test the connection.

## [4. Telling Git about your signing key](https://docs.github.com/en/authentication/managing-commit-signature-verification/telling-git-about-your-signing-key)

1. Open Terminal.
2. Configure Git to use SSH to sign commits and tags: \
   `git config --global gpg.format ssh`
3. To set your SSH signing key in Git, paste the text below, substituting /PATH/TO/.SSH/KEY.PUB with the path to the public key you'd like to use. \
   `git config --global user.signingkey /PATH/TO/.SSH/KEY.PUB`

> Note \
> To push signed commits to GitHub \
> `git commit -S -m "message"`
> Or you can set it as default \
> `git config --global commit.gpgsign true`
