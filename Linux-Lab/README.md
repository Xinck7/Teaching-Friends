# Linux Labs

## Lab 1 Install basic linux machine

1. Deploy linux VM from vagrant

```bash
vagrant init && cp config_file.base Vagrantfile && vagrant up
```

EZ clap you did it! #You too can read instructions

## Lab 2 Install/Start linux gui

1. sign into linux VM
2. install GUI () #might be done from vagrant
3. run the proper init command and open gui
4. (you can uncomment some stuff to fast track setup after running through the manual steps)

## Lab 3 Install STIGViewer

1. believe in the code
2. execute the code
3. download the right checklist
4. sign into GUI (vagrant default is vagrant)
5. Open STIGVIEWER via CLI
6. open checklist

## Lab 4 Deploy Python Flask App

1. Delete current Vagrant if you have done so from labs 1-3
2. Redeploy from template (full uncommented - or snapd commented)
3. Install Python3 #hint package manager install option?
4. Download Flask #get to read docs!
5. Create a requirements.txt and put flask in it
6. Copy paste the minimal application to a <pickyourfilename.py>
7. Start application
8. navigate to localhost in browser

## Lab 5 Docker Deploy Python Flask App

1. Create Dockerfile
2. Write out the best you can the steps from lab4 here using docker docs
3. Docker build image
4. Docker run <image:youjustcreated>
5. navigate to localhost

## Lab 6 Docker deploy with docker-compose same thing

1. docker-compose file using terms:
    - image
    - init
    - container_name
    - ports
    - volumes
    - depends_on:
2. optional part 2 fluentd integration
    - use docs to get the fluentd integration on docker compose #good docs
    - logging:
        driver
        options (address:localhost24224 and async:true)

## Lab 7 Setup using minikube (kubernetes)

1. install minikube
2. create templates
3. Deploy with templates
