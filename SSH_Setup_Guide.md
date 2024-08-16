# Setting Up SSH with GitHub 🔐

Setting up SSH ensures secure communication between your computer and GitHub. Follow these steps to configure SSH:

## 1. Check for Existing SSH Keys

Open your terminal and run:

```bash
ls -al ~/.ssh
```

## 2. Generate a New SSH Key

Next step is to generate an ssh key by running the following command

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

replace `your_email@example.com` with your email address used to register GitHub

## 3. Add Your SSH Key to the SSH-Agent

Run the following command to to start the ssh-agent and add your SSH key:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

## 4. Add SSH Key to Your GitHub Account

Copy your SSH key to your clipboard:

```bash
cat ~/.ssh/id_rsa.pub
```

Go to your [GitHub SSH settings](https://github.com/settings/keys) and add a new SSH key. Paste your key and save it.

## 5. Test Your SSH Connection

Verify your connection with:

```bash
ssh -T git@github.com
```

You should see a success message if everything is set up correctly. 🎉

You're now ready to connect to GitHub using SSH!