# NationalCyberLeagueResource
A list of resources that are useful for the National Cyber League Competition. This list was compiled with the help of many members of the Drury Cyber Defense Team.

## Open Source Inteligence
- [Google](google.com): Google should almost always be your first stop for OSINT questions. 
  - Get familiar with Google's more advanced search operators. [Here](https://static.semrush.com/blog/uploads/files/39/12/39121580a18160d3587274faed6323e2.pdf) is a handy cheat sheet.
- [Wigle](wigle.net): Find and identify wifi networks. 

## Cryptography
- [CyberChef](https://gchq.github.io/CyberChef/): Convert between number bases and encoding schemes
- [Rumkin](https://rumkin.com/tools/cipher/rail-fence/): Encode/Decode railfence ciphers
- [dcode.fr](https://www.dcode.fr/en) Encode/Decode many ciphers. This website is usually one of the first sites on google when you google for a specific cipher.
- [Strings](https://www.howtogeek.com/427805/how-to-use-the-strings-command-on-linux/) The linux strings command will search through any file type and return strings of characters it found. Useful for finding flags in arbitrary file types. 
- [Digital Invisible Ink Toolkit](https://diit.sourceforge.net/): Find messages that are hidden in pictures. Many steganography questions use this tool.
- [Steghide](https://www.kali.org/tools/steghide/): Another way to find messages hidden in a picture.
  - Command to extract message: steghide -sF \<filename\>

## Password Cracking
- [Hash Generator](https://www.browserling.com/tools/all-hashes): You will probably be asked to compute the hashes of some passwords. This site generates many hashes all at once. Select what you need and paste it into the answer box. 
- [Hashes.com](hashes.com): Lookup known hash values here. It is a good first step on any password cracking questions. Often, even a couple of the hard passwords can be found here.
- [Hashcat](https://www.kali.org/tools/hashcat/): Crack password hashes with a wordlist, brute force, or a combination.
  - **Common Flags**
  - -m: Hash Type - Select what type of hash to crack. 0 is an MD5 hash and is most common in NCL. ( -m 0)
  - -a: Attack Mode - Select what type of attack. 0 is a dictionary attack and is most common in NCL. (-a 0)
  - -o: Output - Select what file to output results to. (-O cracked.txt)
  - Example command: hashcat -m 0 -a 0 -o cracked.txt target_hashes.txt wordlist.txt
- [Ophcrack](https://ophcrack.sourceforge.io/): Used to crack windows NTLM hashes. 
  - Download ophcrack [here](https://ophcrack.sourceforge.io/download.php?type=ophcrack)
  - Download table [here](https://ophcrack.sourceforge.io/tables.php): Most password for NCL are found in XP Free Small or XP Free Special.
- [John the Ripper](https://www.kali.org/tools/john/): Used similarly to hashcat. John the Ripper is used to crack password hashes. I am not familiar with John the Ripper amd prefer hashcat so, I will not offer much of a guide on it.

## Log Analysis
- [grep](https://www.geeksforgeeks.org/grep-command-in-unixlinux/): Search for strings or regular expressions to find information in a log. Regular expressions can be a great way to find specific information. But, they can be tricky.
  - **Common Flags**
  - -E: Use regular expressions [Cheat Sheet](https://ryanstutorials.net/linuxtutorial/cheatsheetgrep.php)
  - -o: Only out put the part of the line that matched the regular expression or string
  - -v: Invert the matches. Only output lines that do not match the regular expression or string.
  - -i: Ignore case
  - **Helpful Tips**
  - Pipe the output from one grep statement into another grep statement. This way you can filter down data in stages understand what you are doing.
  - Mix and match flags on consecutive grep statements to fine tune what you are looking for
  - **Example**
  - cat log.log | grep -i "user" | grep -iv "invalid" | grep -E -o "([0-9]{1,3}[\.]){3}[0-9]{1,3}"
  - Explanation: cat the log file and look for any line that contains the word "user" regardless of case to find any line that contains a usernam. Then, grep for anyline that says "invalid" and select only lines that do not match to sort out invalid user attempts. Finally, that last regular expression searches for IP addresses and only outputs the IP address.
- [sort](https://www.geeksforgeeks.org/sort-command-linuxunix-examples/): Sort lines in alphabetical order.
- [uniq](https://www.geeksforgeeks.org/uniq-command-in-linux-with-examples/#:~:text=The%20uniq%20command%20in%20Linux,also%20deletes%20the%20duplicate%20lines.): Remove adjacent duplicate lines. It is important to sort the lines before doing this so that all duplicates are removed (cat log.txt | sort | -uniq)
  - **Common Flags**
  - -c: Return the count of how many duplicate lines there were of each type
- [wc](https://www.geeksforgeeks.org/wc-command-linux-examples/#:~:text=wc%20stands%20for%20word%20count,specified%20in%20the%20file%20arguments.): Return the word count of a file. 
  - **Commmon Flags**
  - -l: Count the number of lines
  - -w: Count the number of bytes in the file
  - -m: Count the number of characters in the file
- [Awk](https://www.geeksforgeeks.org/awk-command-unixlinux-examples/): Awk can be used to scan over files and pull information out by selecting certain fields. Awk is a little more complex than grep but is extremely maleable to do complex analysis. 
- [Excel](https://www.sans.org/white-papers/37745/): Excel can be a great resource to analyze log files quickly. Import a log as a csv file, and change the delimiter to something that makes sense for the log you are looking at. 
- [Python](https://www.pythontutorial.net/python-basics/python-read-text-file/#:~:text=To%20read%20a%20text%20file%20in%20Python%2C%20you%20follow%20these,the%20file%20close()%20method.): Python has amazing utilities to read and write text files. Python can be used for more complex analysis of many log files. 

## Network Traffic Analysis
- [Wireshark](https://www.kali.org/tools/wireshark/): Open, filter, and analyze pcap files.
- [AircapNG](https://www.kali.org/tools/aircrack-ng/#:~:text=aircrack%2Dng%20is%20an%20802.11,or%20simply%20by%20brute%20force.): Analyze wireless traffic and extract the password from unencryptes 802.11 traffic.
  - MORE NEEDED

## Forensics
- [Autopsy]()

## Scanning & Reconnaissance
- [Nmap]()
- [Dirbuster]()
- [Netcat]()
- [Telnet]()

## Web Application Exploitation
- [Burp Suite]()
- [Metasploit]()

## Enumeration & Exploitation
- [Ascii Table]()
- [Python]()
- [Bash]()
- [Python Decompiler]()
- [Ghidra]()

