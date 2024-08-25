# Git Configuration

## Configuration in Windows

1. **Download and Install Kleopatra:**
   - Download and install [Kleopatra](https://gpg4win.org/get-gpg4win.html).

2. **Create a New OpenPGP Key Pair:**
   - Go to `File > New OpenPGP Key Pair...` in Kleopatra.
   - Follow the prompts to create a new certificate.

3. **Export Certificate:**
   - Export the newly created certificate and save it in a secure location.

4. **Import Private Key:**
   - Open PowerShell or Command Prompt and run:
     ```bash
     gpg --import my-private-key.asc
     ```

5. **List Secret Keys:**
   - To list your secret keys, run:
     ```bash
     gpg --list-secret-keys --keyid-format LONG
     ```

6. **Configure Git Signing Key:**
   - Set the signing key for Git with:
     ```bash
     git config --global user.signingkey KEYID
     ```

7. **Set Path for gpg.exe:**
   - Configure Git to use the correct GPG program:
     ```bash
     git config --global gpg.program "C:/Program Files (x86)/GnuPG/bin/gpg.exe"
     ```

8. **List Your GPG Keys:**
   - You can list your GPG keys by running:
     ```bash
     gpg --list-secret-keys --keyid-format LONG
     ```
   - You will see something like:
     ```markdown
     /Users/yourname/.gnupg/secring.gpg
     -----------------------------------
     sec   rsa4096/XXXXXXXXXXXXXXXX 2024-08-18 [SCEA]
     ```
   - Here, `XXXXXXXXXXXXXXXX` is your GPG key ID.

9. **Export Public Key:**
   - To export your public key, run:
     ```bash
     gpg --armor --export XXXXXXXXXXXXXXXX
     ```
10. **Configure Git to Use Your GPG Key:**
    - Set up Git to use your GPG key:
      ```bash
      git config --global user.signingkey XXXXXXXXXXXXXXXX
      ```
    - Replace `XXXXXXXXXXXXXXXX` with your GPG key ID.

11. **Set Git Username:**
    - Configure your Git username:
      ```bash
      git config --global user.name "Your Name"
      ```

12. **Set Git Email:**
    - Configure your Git email:
      ```bash
      git config --global user.email "your.email@example.com"
      ```

13. **Set Up SSH Key (Optional):**
    - If you plan to interact with remote repositories over SSH, generate an SSH key:
      ```bash
      ssh-keygen -t rsa -b 4096 -C "your.email@example.com"
      ```
    - Start the SSH agent and add your SSH key:
      ```bash
      eval "$(ssh-agent -s)"
      ssh-add ~/.ssh/id_rsa
      ```
    - Copy the public key to your clipboard:
      ```bash
      clip < ~/.ssh/id_rsa.pub
      ```
    - Add the key to your GitHub, GitLab, or other Git service account.
