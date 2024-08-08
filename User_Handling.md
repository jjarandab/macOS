# User Handling

```shell
#show admin group members
dscl . -read /Groups/admin GroupMembership

#add user to local admin group
sudo dseditgroup -o edit -a emily -t user admin
sudo dseditgroup -o edit -a emily -t user wheel

#remove user from local admin group
sudo dseditgroup -o edit -d cperson -t user admin


#create  user
sudo dscl . -create /Users/newcom | sudo dseditgroup -o edit -a newcom -t user admin | sudo dseditgroup -o edit -a newcom -t user wheel
sudo /usr/bin/dscl . -passwd /Users/newcom Newcom123!

#delete user
sudo /usr/bin/dscl . -delete "/Users/newcom"

#change password
sudo /usr/bin/dscl . -passwd /Users/paceadmin Admin~123
sudo /usr/bin/dscl . -passwd /Users/newcom MagShow53

#Search Users/paceadmin
/usr/bin/dscl . -search /Users name andrew
```
