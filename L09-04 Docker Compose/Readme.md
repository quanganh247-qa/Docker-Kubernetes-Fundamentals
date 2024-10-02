# L09-04

## Docker compose cheat sheet

![image](https://github.com/user-attachments/assets/a00527fc-465c-4eca-abe8-46595069bdba)


## Build the app

    docker compose build

## Run the app

    docker compose up -d

When the app will run, launch the voting app in your browser http://localhost:5000


## List the containers

    docker compose ps

## Look at the db container logs

    docker compose logs -f web-fe


## Compose V2 commands

![image](https://github.com/user-attachments/assets/c1461459-c3df-4b92-b832-50471d592b43)


LS will list the current projects

    docker compose ls

## Let's try to deploy a second version

    docker compose up -d

This fails because we can only run an app a single time

## Deploy a second version using a different project name

Let's now use a project name to see if we can deploy a second version

    docker compose -p test up -d

This fails because the localhost port 5000 is already assigned.

Change the ports value from

    - "5000:80"

to

    - "5001:80"

## Deploy again

    docker compose -p test up -d

How many versions do we have running?

    docker compose ls

## Cleanup

    docker compose down
    docker compose ls
    docker compose -p test down
    docker compose ls
## Netwoking

![image](https://github.com/user-attachments/assets/b1a03a20-559d-457c-b00b-04abcb9ff5c0)

![image](https://github.com/user-attachments/assets/f2ac7fa7-46b7-4862-a218-f126298562b2)

## Dependence

![image](https://github.com/user-attachments/assets/a63d529a-2219-45d2-b7d8-906d7c6caee7)

Volumes - named

![image](https://github.com/user-attachments/assets/7a7f6f10-5a0a-482b-9ca3-90cebeaeed36)

![image](https://github.com/user-attachments/assets/1669ad86-c6d4-4c9f-9f67-48e3f5031412)

## Restart policy

![image](https://github.com/user-attachments/assets/20bf3966-a1ea-4fdc-a81e-30956a8fef45)

