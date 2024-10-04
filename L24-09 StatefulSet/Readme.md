# L24-09

Let's now create a StafulSet.

![image](https://github.com/user-attachments/assets/88f0cd74-5bfc-436c-8ea5-fd30ac959faa)

![image](https://github.com/user-attachments/assets/4f87bcd4-fa94-4ac6-b3bd-a8497c846365)

![image](https://github.com/user-attachments/assets/327356b5-99a8-47fe-a37e-d18257a4b863)

![image](https://github.com/user-attachments/assets/020b26f7-11b4-416b-9227-d800fe6a405b)

![image](https://github.com/user-attachments/assets/c7d67d17-ceb5-4284-8dc6-2ced99a478b9)

## Create the Deployment

    kubectl apply -f statefulset.yaml

## Get the pods list

    kubectl get pods -o wide

## Get a list of the PersistentVolumes Claims

    kubectl get pvc

## Create a file in nginx-sts-2

Open a session in nginx-sts-2 and create a file in the folder mapped to the volume.

    kubectl exec nginx-sts-2 -it -- /bin/sh
    cd var/www
    echo Hello > hello.txt

## Modify the default Web page

    cd /usr/share/nginx/html
    cat > index.html
    Hello
    Ctrl-D
    exit

## Open a session in nginx-sts-0 and reach nginx-sts-2

    kubectl exec nginx-sts-0 -it -- /bin/sh
    curl http://nginx-sts-2.nginx-headless
    exit

## Delete pod 2

Delete a pod and watch as it is recreated with the same name.

    kubectl delete pod nginx-sts-2

## Is the file still there?

Open a session in nginx-sts-2 and see if the file is still present.

    kubectl exec nginx-sts-2 -it -- /bin/sh
    ls var/www
    exit

## Cleanup

    kubectl delete -f statefulset.yaml
    kubectl delete pvc www-nginx-sts-0
    kubectl delete pvc www-nginx-sts-1
    kubectl delete pvc www-nginx-sts-2
