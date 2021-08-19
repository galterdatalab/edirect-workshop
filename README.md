# edirect-tutorial

# Installation

EDirect will run on Unix and Macintosh computers, and under the Cygwin Unix-emulation environment on Windows PCs. To install the EDirect software, click on the download EDirect installer link to obtain the install-edirect.sh script, then execute it by running:

**source ./install-edirect.sh**

Alternatively, open a terminal window and execute one of the following two commands:

  **sh -c "$(curl -fsSL ftp://ftp.ncbi.nlm.nih.gov/entrez/entrezdirect/install-edirect.sh)"**

  **sh -c "$(wget -q ftp://ftp.ncbi.nlm.nih.gov/entrez/entrezdirect/install-edirect.sh -O -)"**

or copy the following commands and paste them into a terminal window:

  
  **cd ~
  /bin/bash
  perl -MNet::FTP -e \
    '$ftp = new Net::FTP("ftp.ncbi.nlm.nih.gov", Passive => 1);
     $ftp->login; $ftp->binary;
     $ftp->get("/entrez/entrezdirect/edirect.tar.gz");'
  gunzip -c edirect.tar.gz | tar xf -
  rm edirect.tar.gz
  builtin exit
  export PATH=${PATH}:$HOME/edirect >& /dev/null || setenv PATH "${PATH}:$HOME/edirect"
  ./edirect/setup.sh**
  
Any of these methods will download a number of scripts and several precompiled programs into an "edirect" folder in the user's home directory. The setup.sh script may then print an additional command for updating the PATH environment variable in the user's configuration file. The editing instructions will look something like:

  
  **echo "export PATH=\$PATH:\$HOME/edirect" >> $HOME/.bash_profile**
  
As a convenience, the installation process ends by offering to run the PATH update command for you. Answer "y" and press the Return key if you want it run. If the PATH is already set correctly, or if you prefer to make any editing changes manually, just press **Return**.
