## etc/passwd
user1:x:1001:1006::/home/user1:/bin/sh
user2:x:1002:1007::/home/user2:/bin/sh
user3:x:1003:1008::/home/user3:/bin/sh

## logging into new user created, and checking its group
client@client:/etc$ su user1
Password:
$ groups
user1 group1

## after adding new user --> etc/passwd
user1:x:1001:1006::/home/user1:/bin/sh
user2:x:1002:1007::/home/user2:/bin/sh
user3:x:1003:1008::/home/user3:/bin/sh
user4:x:1004:1009::/home/user4:/bin/sh
user5:x:1005:1010::/home/user5:/bin/sh
user6:x:1006:1011::/home/user6:/bin/sh

## Remove user from group
`ansible-playbook playbook.yml -u client --ask-become-pass --tags removeuserfromgroup`
user1:x:1001:1006::/home/user1:/bin/sh
user3:x:1003:1008::/home/user3:/bin/sh
user4:x:1004:1009::/home/user4:/bin/sh
user5:x:1005:1010::/home/user5:/bin/sh
user6:x:1006:1011::/home/user6:/bin/sh
