# OpenHabPi

* https://www.openhab.org/docs/installation/docker.html#installation-through-docker
* Running version `2.5.9`
* Add `--device` option to docker command
* Add z-wave binding (paperui/index.html#/extensions?tab=binding) (probably needed?)
* Paper UI -> Configuration -> Things -> + -> z-wave binding, controller (whatever)
* Paper UI -> Inbox  -> Search For Things (put device in add/discover mode)
* Paper UI -> Configuration -> Things -> click on new thing -> edit to set properties
* Paper UI -> Configuration -> Things -> click on new thing -> Channels -> click on one of them and link the channel to a new item.
* Paper UI -> Control (to control stuff)

# One-off Running On Mac

Plug in the z-stick. To find the device, use the [manual](https://aeotec.freshdesk.com/support/solutions/articles/6000092802-z-stick-gen5-quick-start-just-the-essentials) `ls /dev/cu.usbmodem*`.

```sh
mkdir -p ~/Documents/openhab/conf && mkdir ~/Documents/openhab/userdata && mkdir ~/Documents/openhab/addons
```

```sh
docker run \
        --name openhab \
        --net=host \
        -v /etc/localtime:/etc/localtime:ro \
        -v ~/Documents/openhab/conf:/openhab/conf \
        -v ~/Documents/openhab/userdata:/openhab/userdata \
        -v ~/Documents/openhab/addons:/openhab/addons \
        --device ...... \
        openhab/openhab:latest
        
# -v /etc/timezone:/etc/timezone:ro \
```

