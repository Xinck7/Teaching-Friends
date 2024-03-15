# Windows Labs

## in AWS be sure to delete when you are done or at least turn them off!! #doesn't cost when its off for most resources

1. ec2 instances
2. vpc
3. subnet

## Lab 1 deploy a client/server

1. Deploy "win-test-server" Windows server 2022 (diff OS but just looks like normal windows really just has more stuff it can do) (VM possibly space dependant but likely need to do this on AWS only)
2. Deploy "dc01" Windows Server 2022 (or latest year)
    select default ami/free tier settings (create new vpc and create new key pair and then click launch)
    wait for it to setup all the way


## Lab 2 Setup a local policy

1. setup local policy on windows computer
<!-- Need to fill in what is required for this/what policy is getting set lock screen timeout 1 min maybe? -->

## Lab 3 Setup AD DC

1. Install ADDS on windows server
2. connect via RDP to your server 
    need to have the private key and decrypt the password for the admin/pass settings
3. server manager
4. manage
5. add feature/role
6. active directory domain services -> good to click through after that
7. after install go to the ADDS tab in server manager
8. finish setup
    create new forest
        fangorn.com

9. it'll restart when its done and you'll use the same admin/pass for the ec2 for the rdp session as last time - domain creds for joining new machines

## Lab 4 Setup domain user and admin user

Goals: include permissions for both
1. open ADUC (active directory users and computers)
    server manager tools aduc
2. create admin-user
    pass     Tr33B@3rd and not change on first login
3. give it permissions by joining to domain-admins group
4. create test-domain-user
    pass Abcd!234
    let it default credentials groups wise


## Lab 5 Setup and join computer to computer OU

1. Setup OU group for domain computers
2. login to the win-test-server
3. file explorer -> system props -> rename this PC (advanced) -> change at bottom
4. add security group settings to setup traffic rules between the hosts
5. set the DC as the dns server for the client
6. rename as member of fangorn.com
7. fangorn.com\domain-admin (whatever the userlogon name is in the account props) and password
8. check you can sign in with domain credentials instead of admin credentials

## Lab 7 Place Windows in right OU

1. on the DC find the new computer
2. drag and drop into the right OU
3. enforce (gpupdate /force on client or right click and do it to em)

## Lab 8 Create GPO Policy with different setting than local policy for screen lockout

1. google to implement a GPO policy to set screen lockout to 5 mins 

## Lab 9 Setup OU nested rules 1 deep to illustrate priority

1. have a nested OU that sets it to 10 mins

## Lab 10 Set DC to be domain admin only login

1. google to implement a GPO that applies just to the domain controllers that only domain admins can login
2. test with domain-admin and user-accounts
