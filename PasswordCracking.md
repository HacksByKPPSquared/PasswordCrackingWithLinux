Lab 02: Password Cracking with Linux

1.  Cracking Linux Passwords

    1.  Creating User Accounts and Groups

<!-- -->

1.  Launch the Kali virtual Machine to access the graphical login
    screen.

2.  Log in as root with that password toor.

3.  Open a new terminal window by clicking on the terminal icon located
    in the top menu pane.

> <img src="./media/image1.png"
> style="width:2.42742in;height:0.27087in" />

4.  Type the command below, followed by pressing the Enter key to view
    the groups on the system.

> root@Kali Attacker:~# cat /etc/ group

<img src="./media/image2.png" style="width:4.70704in;height:2.8354in" />

5.  Enter the command below to p juniors and seniors . opulate the group
    list by creating two new groups

    1.  root@Kali Attacker:~# groupadd juniors

    2.  root@Kali Attacker:~# groupadd seniors

> <img src="./media/image3.png"
> style="width:3.42756in;height:0.50007in" />

6.  Confirm that the groups have been added using grep .

> root@Kali Attacker:~# cat /etc/group \| grep “ seniors ”
>
> <img src="./media/image4.png"
> style="width:4.84443in;height:0.56258in" />
>
> root@Kali Attacker:~# cat /etc/group \| grep “juniors”
>
> <img src="./media/image5.png"
> style="width:4.71941in;height:0.60425in" />

7.  Enter the command below to view the user accounts on the system.

> root@Kali Attacker:~# cat /etc/passwd
>
> <img src="./media/image6.png" style="width:7.0114in;height:3.52132in" />

8.  Add users **elmo** and **Oscar** to the system and assign them to
    the group **seniors**.

> root@Kali Attacker:~# useradd elmo g seniors
>
> root@Kali Attacker:~# useradd oscar g seniors
>
> <img src="./media/image7.png"
> style="width:4.16725in;height:0.50007in" />

9.  Add users l isa and homer and assign them to the group juniors

> root@Kali Attacker:~# useradd lisa g juniors
>
> root@Kali Attacker:~# useradd homer g juniors
>
> <img src="./media/image8.png"
> style="width:4.13599in;height:0.60425in" />

10. View the created . /etc/ passwd file once more to verify that all
    accounts are successfully

> root@Kali Attacker:~# cat /etc/passwd
>
> <img src="./media/image9.png"
> style="width:3.45882in;height:0.93763in" />
>
> 11\. View the /etc/shadow file and observe the values next to the
> newly created accounts towards the bottom of the list
>
> root@Kali-Attacker:~# cat /etc/shadow
>
> <img src="./media/image10.png" style="width:3.06931in;height:3.7127in"
> alt="A screenshot of a computer Description automatically generated" />
>
> 12\. Configure passwords for the users: elmo, oscar, lisa, and homer.
> First, begin by configuring the password for the elmo user account.
>
> root@Kali-Attacker:~# passwd elmo
>
> 13\. When prompted for the new password, type 123123 followed by
> pressing the Enter key. When prompted to retype the password, enter it
> again.
>
> <img src="./media/image11.png" style="width:4.125in;height:1.09722in"
> alt="A close-up of a computer screen Description automatically generated" />
>
> 14\. Configure the password for oscar next. When prompted, enter
> sanjose as the password.
>
> root@Kali-Attacker:~# passwd oscar
>
> 15\. Configure the password for lisa. When prompted, enter academic as
> the password.
>
> root@Kali-Attacker:~# passwd lisa
>
> 16\. Configure the password for homer. When prompted, enter acapulco
> as the password.
>
> root@Kali-Attacker:~# passwd homer
>
> 17\. Type the command below to view the new user accounts along with
> their respective hashes in the shadow file. The command options used
> below will only output the last four accounts in the shadow file.
>
> <img src="./media/image12.png" style="width:8.41667in;height:1.94444in"
> alt="A computer screen with white text Description automatically generated" />
>
> 18\. Leave the terminal open to continue with the next task.

1.2. **Cracking Passwords on a Linux System Using John the Ripper**

> **1.** Before using John the Ripper, using the terminal, type the
> command below to view the available options that can be used with the
> application. This is useful when using any command in Linux.
>
> **root@Kali-Attacker:~# john -help**
>
> <img src="./media/image13.png" style="width:8.56944in;height:5in"
> alt="A computer screen shot of a computer screen Description automatically generated" />
>
> 2\. Run John the Ripper against the /etc/shadow file using a wordlist
> called passlist.
>
> <img src="./media/image14.png" style="width:7.23565in;height:2.58416in"
> alt="A computer screen with white text Description automatically generated" />

3\. Leave the terminal open to continue with the next task.

2\. **Cracking Windows Passwords**

**2.1. Cracking Windows Passwords Using Hashcat**

1\. While on the Kali system, focus on the terminal window.

2\. Change to the /tmp/hashes directory.

root@Kali-Attacker:/tmp/hashes# cat winhashes

> <img src="./media/image15.png" style="width:7.875in;height:2.97222in"
> alt="A screenshot of a computer screen Description automatically generated" />
>
> 3\. View the winhashes file extracted from a Windows system. Notice
> the usernames listed along with the associated password hashes.

<img src="./media/image16.png" style="width:3.56944in;height:0.5in"
alt="A red and blue text Description automatically generated" />

root@Kali-Attacker:/tmp/hashes# cat winhashes

> <img src="./media/image17.png" style="width:7.80556in;height:2.94444in"
> alt="A computer screen with white text Description automatically generated" />

4\. Parse out the NTHash from the winhashes file.

> root@Kali-Attacker:/tmp/hashes# cat winhashes \| awk –F”:” ‘{print
> \$3}’
>
> <img src="./media/image18.png" style="width:6.55556in;height:2.81944in"
> alt="A computer screen with white text Description automatically generated" />
>
> 5\. Now that we have confirmed what is needed to be parsed out, save
> the output to a file named nthashes.
>
> <img src="./media/image19.png"
> style="width:7.90278in;height:0.65278in" />

6\. Verify that the NTHashes have outputted correctly in the nthashes
file.

root@Kali-Attacker:/tmp/hashes# cat nthashes

> <img src="./media/image20.png" style="width:4.54167in;height:2.73611in"
> alt="A computer screen with white text Description automatically generated" />
>
> 7\. Run the Hashcat password cracking program against the nthashes
> file with the help of the passlist dictionary file in an attempt to
> crack the NTHashes from a Windows system. If asked to accept a EULA,
> type **YES** followed by pressing Enter.

root@Kali-Attacker:/tmp/hashes# hashcat –m 1000 nthashes

/tmp/wordlists/passlist

<img src="./media/image21.png" style="width:7.41858in;height:4.26733in"
alt="A screenshot of a computer Description automatically generated" />

8\. Leave the terminal open to continue with the next task.

3\. **Obtaining and Cracking Linux /etc/shadow**

3.1. **Obtaining the /etc/shadow Remotely**

1\. Launch the DVL virtual machine.

2\. Log in as root, using toor as the password.

> 3\. At the prompt, type **startx** followed by pressing the **Enter**
> key to launch the GUI.
>
> 4\. Open a new terminal window by clicking on the **Terminal** icon
> located on the bottom menu pane.
>
> <img src="./media/image22.png" style="width:4.86111in;height:1.44444in"
> alt="A screen shot of a computer Description automatically generated" />
>
> <img src="./media/image23.png"
> style="width:3.45833in;height:0.36111in" />

5\. Type the command below to initialize the FTP service.

bt ~# proftpd

> <img src="./media/image24.png" style="width:5.76389in;height:0.79167in"
> alt="A black background with white text Description automatically generated" />

6.  Change focus to the Kali system.

> 7\. While on the Kali system, focus on the terminal window. Remotely
> FTP into the DVL Server. When asked for a username, type root followed
> by pressing Enter. When prompted for the password, type toor followed
> by pressing Enter.
>
> root@Kali-Attacker:/tmp/hashes# ftp 10.1.1.10

<img src="./media/image25.png" style="width:7.52778in;height:1.97222in"
alt="A screen shot of a computer Description automatically generated" />

8\. Once connected to the DVL system via FTP, print the current
directory.

ftp\> pwd

> <img src="./media/image26.png" style="width:3.38889in;height:0.70833in"
> alt="A close up of a sign Description automatically generated" />

9\. Change to the /etc directory.

ftp\> cd /etc

> <img src="./media/image27.png" style="width:3.16667in;height:0.68056in"
> alt="A black background with white text Description automatically generated" />

10\. Download the local shadow file on the DVL system via FTP.

ftp\> get shadow

> <img src="./media/image28.png" style="width:6.84722in;height:1.44444in"
> alt="A screen shot of a computer Description automatically generated" />

11\. After the shadow file successfully downloads, close the FTP
session.

ftp\> exit

> <img src="./media/image29.png" style="width:3.47222in;height:0.68056in"
> alt="A red and blue text Description automatically generated" />
>
> 12\. Verify that the shadow file has transferred into the current
> directory (/tmp/hashes).
>
> root@Kali-Attacker:/tmp/hashes# ls -l
>
> <img src="./media/image30.png" style="width:5.26389in;height:1.69444in"
> alt="A screenshot of a computer screen Description automatically generated" />

13\. Leave the terminal open to continue with the next task.

3.2. **Cracking /etc/shadow With Johnny**

> 1\. While on the Kali system, observe the content of the recently
> transferred shadow file. Notice the list of users.

root@Kali-Attacker:/tmp/hashes# cat shadow

> <img src="./media/image31.png" style="width:6.26389in;height:4.90278in"
> alt="A screenshot of a computer Description automatically generated" />
>
> 2\. Start the GUI password cracking application, johnny. This is the
> same as John the Ripper but with a graphical user interface. Type the
> command below in the terminal window. Press Enter
>
> root@Kali-Attacker:/tmp/hashes# johnny

3\. A new window appears. Click on the **Open Passwd File** icon.

<img src="./media/image32.png" style="width:5.65278in;height:1.47222in"
alt="A screenshot of a computer Description automatically generated" />

4\. In the new *Open* window, navigate to the **/tmp/hashes** directory.
Select the **shadow**

> file and click on the **Open** button.
>
> <img src="./media/image33.png" style="width:5.71287in;height:4.07412in"
> alt="A screenshot of a computer Description automatically generated" />
>
> 5\. On the Passwords screen, notice how each column is populated with
> its associated values. Click on the Options icon located in the left
> pane.

<img src="./media/image34.png" style="width:6.47525in;height:4.9066in"
alt="A screenshot of a computer Description automatically generated" />

6.  On the Options screen, select the radio button next to Wordlist
    mode. Notice the

pane on the bottom changes to the Wordlist tab.

<img src="./media/image35.png" style="width:6.84783in;height:5.34654in"
alt="A screenshot of a computer Description automatically generated" />

7\. In the bottom pane, click on the Browse button.

<img src="./media/image36.png" style="width:8.73611in;height:2.18056in"
alt="A screenshot of a computer Description automatically generated" />

8.  In the Open window, navigate to the /tmp/wordlists directory. Select
    the passlist file and click on the Open button.

> <img src="./media/image37.png" style="width:6.91666in;height:4.97222in"
> alt="A screenshot of a computer Description automatically generated" />
>
> 9\. Verify that the Wordlist file is assigned to
> /tmp/wordlists/passlist. Click the Start Attack icon located on the
> top menu

10\. Notice the progression bar at the bottom. When it reaches 100%,
click the

Passwords icon from the menu located on the left to view the results.

<img src="./media/image38.png" style="width:7.27104in;height:5.6348in"
alt="A screenshot of a computer Description automatically generated" />
