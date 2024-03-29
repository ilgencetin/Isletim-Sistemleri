'[student@workstation ~]$ lab start cli-desktop'
  - workstation makinası üzerinde student kullanıcısısın. lab environmentın tüm gerekliliklerini sağladığından emin olma kodu.
 - 'finish' command student şifresini student yapar.
 - 'passwd' şifreyi başka bir şifreye değiştirmeni sağlar. 
 - 55TurnK3y'e çevir şifreyi.
 - whoami 
 - date
 - date +%R 
 - date +%x
 - file --> dosya aramana yardımcı olur
 - etc 
 - bin
 - head --> görmek istediğin kısmın başını gösterir.
 - tail -n3 --> görmek istediğin kısmın son 3 satırını gösterir
 - cat -->  this command to create single or multiple files, view the contents of files, concatenate the contents from various files, and redirect contents of the file to a terminal or to files.
 - taba bir kez basarsan tamamlar, iki kez basarsan öneri listesini çıkarır koda benzer.
 - useradd --> create users on the system 
 - \ birden çok commandi aynı lineda yazmak için kullanılır 
 - > secondary prompt, default olarak gelen command ayırıcı. DİKKATLİ OLMALISIN, OUTPUT direction olarak sayılmamalı
 - history --> önceden kullanılan commandler 
 - !number --> önceki commandleri tekrar yazmadan expand eder 
 - !string --> specified string için commandi expand eder.
 - ![image](https://user-images.githubusercontent.com/113854816/206909579-4ea02f18-891e-4b02-9da9-c1506eeedab9.png)
 - wc --> display the number of lines word and bytes
 -  file-system directory contents:
 -  Static content remains unchanged until explicitly edited or reconfigured.
 -  Dynamic or variable content might be modified or appended by active processes
 -  Persistent content remains after a reboot, such as configuration settings.
 -  Runtime content from a process or from the system is deleted on reboot.

![image](https://user-images.githubusercontent.com/113854816/206910060-dcde8443-1912-4452-82fc-97d27003fa62.png)

- Boşluk karakteri linuxta file ismine dahil olabilir. command lineda boşluklar distinguish etmek için kullanılır, eğer fileda boşluk karakteri varsa ve öyle yazılırsa --> to avoid this mistake, surround such file names in quotation marks so that the shell interprets the name as a single argument. 
- _absolute path of a file_ /path_name/ 
- örnek verirsek: /var/log/messages
- _relative path_ Relative path names follow a simple rule: a path name with anything other than a forward slash as the first character is a relative path name. For example, relative to the /var directory, the message log file is log/messages.
- _relative path'te working directory üzerinden lokasyon gösterilir._
- pwd --> working directorydeki full path name'i gösterir.
- ls --> lists directory contents for the specified directory
- ls -l --> long listing format 
- ls -a --> all files, including hidden ones
- ls -R recursive to include the contents of all subdirectories
- cd --> change shell's current working directory. 
- prompt displays ~ --> when your current working director is your home directory.
- touch --> updates the time stamp of a file to the current date and time without otherwise modifying it, creating empty files
- file names starts with (.) dot --> hidden files 
- tilde (~) special character in combination with other commands to facilitate the interaction with the home directory.
- The cd .. command uses the (..) hidden directory to move up one level to the parent directory, without needing to know the exact parent name. The other hidden directory (.) specifies the current directory on commands where the current location is either the source or destination argument, and avoids the need to type the directory's absolute path name.
- 	Which command creates an empty file called helloworld.py in the user home directory, assuming that your current directory is /home? touch ~/helloworld.py
- 	Which command changes the working directory to /tmp if the current working directory is /home/student? cd ../../tmp
- 	**mkdir** creates one or more directories or subdirectories
- If the directory exists, or a parent directory of the directory that you are trying to create does not exist, then the mkdir command fails and it displays an error. 
- **mkdir -p** creates missing parent directory (ch1 ch2 ch3 üreteceksin ama tez başlığı altında, o zaman _mkdir -P tez/ch1 tez/ch2 tez/ch3/tez_
- **cp** copies a file and creates a file either in the current directory or in a different specified directory
- _cp commandi directory kopyalamaz, sadece file kopyalar, tez_chp1.tct kopyalar ama tez'i kopyalamaz._
- **cp -r** directory kopyalarız 
- . ya da .. da kullanılabilir.
- **mv** dosyaların yerini değiştirir. mv değiştirmek istediğin file.txt değiştirilen isim.txt
- **mv -v** dosyalarda ne değişiklik yapıldığını detaylı olarak gösterir. 
- [user@host Documents]$ ls Thesis/Chapter1
[user@host Documents]$
[user@host Documents]$ mv -v thesis_chapter1.txt Thesis/Chapter1
renamed 'thesis_chapter1.txt' -> 'Thesis/Chapter1/thesis_chapter1.txt'
[user@host Documents]$ ls Thesis/Chapter1
thesis_chapter1.txt
[user@host Documents]$ ls -l
-rw-r--r--. 1 user user 11431 Mar  7 14:39 thesis_chapter2_reviewed.txt
...output omitted...
- **rm** dosya siler.
- **rm -r** directoryi siler 
- **rm -i** dosyaları silmeden önce doğrulama ister.
- **rm -f** dosyaları doğrulamadan forcelayarak direkt siler.
- **rmdir** boş directoryleri silmek için kullanılır.
- **ln** hard link oluşturmak için gerekli command, halihazırda bulunan bir file'ı point eder, commandin içine iki argüman yazmalısın: file'ın pathi ve hard link eklemek istediğin path
- **ln -il** inode numberı ekler. eğer iki kısımın da inode numberı eşitse demdk ki filelar hard linklenmiştir ve aynı data contentini içeriyorlardır.
- **df** hangi file systemlerinin ne içerdiğini gösterir. mounted on kısmından file system hiyerarşisini görebilirsin. 
- _ln commandini kullanırken dosyaların aynı directory ya da subdirectory içerisinde olmaları gerekir. mounted on kısmından baktığında aynı directoryde değillerse ln kullanılamaz!!!_
- **ln -s** sembolik hard link oluşturmanı sağlar. outputta lrwxrwxrwx kısmında l görüyorsan bu sembolik hard linktir.
- **cd -P** update the current working directory by using the name of the actual directory

##### PATTERN MATCHING 
![image](https://user-images.githubusercontent.com/113854816/206994516-8d27d324-6f9b-4de9-bcff-ed504a02e81b.png)
- **ls a*** ayla başlayan kelimeleri matchler 
- **ls *b** son harfi b olan kelimeleri matchler
- **ls *a*** a barındıran kelimeleri matchler 
- **ls [ac]*** a veya cyle başlayan bütün kelimeleri matchler 
- **ls [!b]*** ilk harfi b olmayan kelimeleri matchler
- **ls ????** 4 harf barındıran kelimeleri matchler 
- The tilde character (~), matches the current user's home directory. If it starts with a string of characters other than a slash (/), then the shell interprets the string up to that slash as a user name, if one matches, and replaces the string with the absolute path to that user's home directory. If no user name matches, then the shell uses an actual tilde followed by the string of characters.
- **echo** display the value of the tilde charachter 
###### BRACE EXPANSION 
- **echo {Sunday, Monday, Tuesday, Wednesday,}.log** output ayrı ayrı loglu yazılmış hali olarak çıkar.
- **echo file{a{1,2},b,c}.txt** output --> filea1.txt filea2.txt fileb.txt filec.txt
- practical use: **mkdir ../RHEL{7,8,9} ls ../RHEL***
###### VARIABLE EXPANSION 
- **USERNAME=operator**
- **VARIABLENAME=value**
- **echo $USERNAME**
- _yanlış yazımı elimine etmek için ${USERNAME} şeklinde de yazabilirsin._
- Variable names can contain only letters (uppercase and lowercase), numbers, and underscores. Variable names are case-sensitive and cannot start with a number.
###### COMMAND SUBSTITUTION 
- **echo Today is $(date +%A)
- _eğer birlikte yazmak istiyorsan dolar işaretini koyman gerekiyor._
- _\ kullandığın zaman direkt yazılan şeyi çıktı etmiş olursun. \$HOME yazdığın zaman expand edilmiş bilgiyi değil direkt \$HOME çıktı edilir._
- Single quotation marks stop all shell expansion. 
- Double quotation marks stop most shell expansion.
- [user@host glob]$ echo "Will variable $myhost evaluate to $(hostname -s)?"
Will variable host evaluate to host?
[user@host glob]$ echo 'Will variable $myhost evaluate to $(hostname -s)?'
Will variable $myhost evaluate to $(hostname -s)?

#### CREATE, VIEW AND EDIT TEXT FILES 
![image](https://user-images.githubusercontent.com/113854816/207040621-e38a5684-b0da-480a-b90b-ac2aedaf88b5.png)

- **pipelines:** sequence of one or more commands that are seperated by the vertical bar character. 
- **ssh** remotte logins

#### GET STARTED WITH VIM
- The u key undoes the most recent edit.
- The x key deletes a single character
- The :w command writes (saves) the file and remains in command mode for more editing.
- The :wq command writes (saves) the file and quits Vim.
- The :q! command quits Vim, and discards all file changes since the last write.

#### SHELL VARIABLE 
- **set** list all shell variables that are currently set 
- **set | less** less komudu bir sayfada okumana yardımcı olur.
- variable expansion burada da uygulayabilirsin. 
- **alias** sürekli kullandığın bir bash fonksiyonu varssa alias ile yazabilirsin.
- ex: **alias hello= echo "Hello, this is a long string."
- **unset** daha önce ayarlanmış variable'ı siler
- **export -n** unexport a variable without unsetting it
- **unalias** to unset a alias

- **id** --> show info about the currently logged-in user 
- **id user01** username'i de ekleyerek yazdığında diğer userla ilgili bilgi alırsın 
- **ls -l dosya_adi.txt** dosyanın sahibini çıktı verir
- **ls -ld Documents** directory'nin sahibini verir
- **ps** proses infosunu verir
- **ps -a** terminaldeki bütün prosesleri verir 
- **ps -u** prosesle ilgili olan userı verir 
- **cat /etc/passwd/** yukarıdaki commandlerin çıktılarında aslında username'i alırız, UID'ye ihtiyacımız varsa bu kodu kullanırız çünkü dosyalarda burada tutulur
- /bin/bash : The default shell program for this user that runs at login. Some accounts use the /sbin/nologin shell to disallow interactive logins with that account.
- **cat /etc/group/** aslında belli dosyalara erişimini istediğimiz gruplar olabilir. bunları bu komutla bulabiliriz.
- **_EXAMPLE_** Which item represents the program that provides the user's command-line prompt? _LOGIN SHELL_

#### GAIN SUPERUSER ACCESS
- **su - username** kullanıcı farklı bir user account'ına geçebilir. eğer normal bir user olarak switch etmek istiyorsan password girmelisin değiştireceğin user için. eğer _root_ kullanıcıysan şifre sormaz.
- **su ya da su -** komutunu direkt kullanırsan, username vermeden --> direkt root kullanıcıya girmeye çalışırsın.
- **sudo** komutuyla geçici olarak _root_ user priviligeları kazanırsın. authentication için halihazırda kullandığın hesabın şifresini girmen yeterlidir. ne başka bir userın, ne de root hesabın şifresine ihtiyaç duyarsın. 

![image](https://user-images.githubusercontent.com/113854816/207081557-21168624-5ec3-4994-a5c7-28fe31f181dc.png)

- **sudo** komutu kullanılan bütün komutları /var/log/secure'e kaydeder.
- **sudo -i** _root_ accounta ulaşmak için kullanılır 
- **sudo -s** run the shell without the interactive scripts
![image](https://user-images.githubusercontent.com/113854816/207082372-914b1f12-2175-4f1f-a20c-5fddef734c72.png)

- **_ŞİFREYİ EN SON ozlemozlem YAPTIN_**

###### LOCAL USER 
![image](https://user-images.githubusercontent.com/113854816/207103851-4c975921-8bf0-4af1-9199-e080698a7d5e.png)
- **useradd** user ekleme
- **userdel** user silme
- **userdel -r** username'i /etc/passwd dahil olmak üzere her yerden siler. eğer userdel -r yapmadan kullanıcı yüklersen bu UID unassigned olarak kalır. üzerine bir kullanıcı atanırsa security problemi olur.

**UID RANGES**
- **UID 0** superuser (root) account UID 
- **UID 1-200** system account UIDs statically assigned to system processes.
- **UID 201-999** do not own files on system 
- **UID 1000+** regular unprivigeled user accounts

#### MANAGE LOCAL GROUP ACCOUNTS 
- **groupadd** grup ekleme, eğer yeteri kadar bilgi verilmezse sıradaki uygun GID numarasından maksimum olanına iletir direkt. 
- **groupadd -g 10000** bir GID numarası assign edersin
- **groupadd -r** system groupları create eder
- **groupmod** grup üzerinde değişiklik yapılmasını sağlar 
- **groupmod -n groupyeniisim groupeskiisim** grubun ismini değiştirmeni sağlar.
- **groupmod -g 20000 group2** yeni GID numarası vermeni sağlar 
- **groupdel** grup siler
- **usermod -g group01 user02** userın grubunu değiştirme
- **usermod -aG grup01 user03** userı secondary grupa ekleme
- **newgrp group1** geçici olarak grubunu değiştirmek


#### MANAGE USER PASSWORDS
- **/etc/shadow** encrypted passwords list
- user03:$6$CSsXsd3rwghsdfarf:17933:0:99999:7:2:18113:
![image](https://user-images.githubusercontent.com/113854816/207117007-0e98d97b-7d10-4eb9-9d38-42b5fa7a0d5d.png)

- $6$CSsXcYG1L/4ZfHr/$2W6evvJahUfzfHpc9X.45Jc6H30E
- 6 --> SHA-512 hashing algorithm 
- 5 --> SHA-256
- 1 --> MD5
- sXcYG1L/4ZfHr: The salt in use to encrypt the password; originally chosen at random.
- 2W6evvJahUfzfHpc9X.45Jc6H30E: The encrypted hash of the user's password; combining the salt and the unencrypted password and then encrypting to generate the password hash.
- **chage** implementation of password aging policy
- **chage -m 0 -M 90 -W 7 -I 14 sysadmin1**
- -m minimum gün -M maksimum gün
- -W warning period 
- -I inaktif period 
- -d password değiştirme zorunluluğu
- **chage -E** change expiration date 
- **chage -l** display the password aging policy 
- **usermod -L** locks user account and the user cannot log into the system
- eğer bir kullanıcı kesin bir tarihte işten çıkacaksa kod: **_usermod -L -e 2022-08-14 cloudadmin10_**
- **usermod -U** userın tekrar accounta erişimini engelle
- **usermod -s /sbin/nologin newapp** newappe erişimini engeller. 

#### PERMISSIONS 
- user permission
- group permission 
- other permissions
- special permissions
- **permission types: _read, write, execute (files can be executed as commands_)
- **ls -l** shows detailed info about permissions and ownership 
- **ls -ld/home** directory hakkında detailed infoyu gösterir. contenti göstermez!!
- **-** regular file
- **d** directory 
- **l** symbolic link 
- **c** character device file
- **b** block device file 
- **p** named pipe file
- **s** local socket file 
- **rwx _string_** set has all permissions: read, write, execute
- **-** means that no permission given 
- **chmod** modify file and directory permissions **chmod Who/What/Which file|directory**
- **u _user_, g _group_, o _other_ a _all** 
- **+ _add_, - _remove_, = _set exactly_**
- **r _read_, w _write_, x _execute_, X _special execute_**
- execute permissions for everyone: [user@host ~]$ chmod a+x myscript.sh
- Remove read and write permission for group and other: [user@host ~]$ chmod go-rw document.pdf
- **-R** kullanıldığı zaman permissions on the files in an enitre directory _tree_. : [user@host ~]$ chmod -R g+rwx /home/user/myfolder
- **Octal method: chmod ### file/directory** ### digiti temsil eder.
- _NOTE:_ Start with 0.If you want to add read permissions for this access level, then add 4. If you want to add write permissions, then add 2. If you want to add execute permissions, then add 1.
- **chown** changes owner of the file/directory tree depending on -R 
- **chowm :admins Pictures** :admins yeni yetkileri admins grubuna verir. 
- **visitor:admins** eklediğinde admins grubu içindeki visitor userına verilir ownerlık.
- **SPECIAL PERMISSIONS:**
- **suid: u+s**
- **sgid: g+s**
- **sticky: o+t**

###### DEFAULT PERMISSIONS 
- **umask** is an octal bitmask that clears the permissions of new files and directories that a process creates.

- **_NOTE_**
- File ownership permissions have three categories. A file is owned by a user, a single group, and other users. The most specific permission applies. User permissions override group permissions and group permissions override other permissions.
- The ls command -l option expands the file listing to include both the file permissions and ownership.
- The chmod command changes file permissions from the command line.
- The chmod command can use one of two methods to represent permissions: symbolic or octal.
- The chown command changes file ownership. The chown command -R option recursively changes the ownership of a directory tree.
- The umask command without arguments displays the current umask value of the shell. Every process on the system has a umask. The default umask values for Bash are defined in the /etc/profile and /etc/bashrc files.
- The suid, sgid, and sticky special permissions provide additional access-related features to files.


#### MANAGE PROCESSES 
![image](https://user-images.githubusercontent.com/113854816/207246080-95cb084b-7ddd-43a0-a6af-60bc94a49c7c.png)

- **top** command S column --> shows the state of each process
- **ps** command STAT --> shows the state of each process
- **ps** used for listing detailed info for current processes. 
- **stdout** controlling terminal 
- **ps aux** displays all processes including processes without a controlling terminal
- **ps lax** provides more detail and displays faster by avoiding username lookups. 
- **ps -ef** display all processes 
- **exiting or defunct** zombie processes are listed
- **ps --forest** display the processes in a tree format so you can view relationships between parent and child processes.
- **ps -O and --sort** sorts the output.
- **&** any command or pipeline can be started in the background by appending
- **sleep** 
- **|** the PID of the last command in the pipeline is displayed. 
- **jobs** display the list of jobs for the shell's session 
- **fg** bring a backgorund job the foreground. Use the the (%jobNumber) format to specify the process to foreground.
- **Ctrl+Z** send a foreground process to the background
- **ps j** displays info about jobs 
- **bg** start running the suspended process with **%id**

###### KILL PROCESSES
![image](https://user-images.githubusercontent.com/113854816/207249546-68dd4d6c-82fa-471a-b4fb-81a471027e0a.png)

- **kill -l** available signalleri ortaya çıkarır 
- **kill ID** prosesi kill
- **killall** can signal multiple processes 
- **pkill** signal one or more processes that match selection criteria.
- **w** list user logins 
- **pgrep** identify the PID numbers
- **uptime** displat the current load average
- **lscpu** the number of CPUs that are present on a system 
- **top** displays a dynamic view od the system's processes and a summary header followed by a process or thread list 

![image](https://user-images.githubusercontent.com/113854816/207251029-c9246377-890e-4fb4-86bb-85603ccd318a.png)

