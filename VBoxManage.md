# VBoxManage commands

## list vms
```
VBoxManage list vms
```

## list running vms
```
VBoxManage list runningvms
```
## stop vm and save its data

```
VBoxManage controlvm "MACHINEID" savestate
```

## stop all running vms and save their data oneliner
```
for x in $(VBoxManage list runningvms | awk '{print $2}'); do echo "Stopping $x ..."; VBoxManage controlvm $x savestate; done
```
