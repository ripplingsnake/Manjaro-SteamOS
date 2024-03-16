> [!NOTE]
> ### DUE TO RECENT CHANGES IN MANJARO
> After install go to Add/Remove Software and remove `steam-deckify`, then reinstall it and select steam os with HHD session, this fixes the new updates!

> [!IMPORTANT]
> You will need a mouse, keyboard, usb drive, and a usb hub (preferably with power passthru, but not required).

# This is a unique take of Steam OS on linux.

## Installation

Download Manjaro KDE Plasma full image from [here](https://manjaro.org/download/).

Once installed open Konsole, install steam and log into your account.

```sh
sudo pacman -Sy 
sudo pacman -S steam
```

Clone this repository into your Downloads folder
```sh
cd ~/Downloads
git clone https://github.com/ripplingsnake/Manjaro-SteamOS.git
cd ./Manjaro-SteamOS
```

After it's cloned run the first script
```sh
chmod +x ./install_first.sh
./install_first.sh 
```

After it has finished, run it again with `sudo`.
```sh
sudo ./install_first.sh
```

> [!IMPORTANT]
> Open `System Settings` then go to `Startup and Shutdown`, at the bottom center left of the window click behaviour. Then and make sure log in again after logging off is checked.

> [!IMPORTANT]
> **Reboot**


After rebooting, run the second script
```sh
chmod +x ./Install_2nd.sh
sudo ./Install_2nd.sh
```

> [!TIP]
> Your fan curves can be adjusted in PowerControl from SteamOS.

# Optional

## 3d sound improvement in SteamOS for the ROG Ally

Downlaod `Easy Effects` from Add/Remove Software.

Copy `pipewire.conf.d` and the four `.wav` files to `/etc/pipewire`
```sh
sudo cp ./pipewire.conf.d /etc/pipewire -R
sudo cp *.wav /etc/pipewire
```

Copy `sound.service` to `/etc/systemd/system`
```sh
sudo cp sound.service /etc/systemd/system
```

Then run
```sh
sudo systemctl enable --now sound.service
```

> [!IMPORTANT]
> **Reboot**

Goto sound settings on desktop you will see new sound sinks, move all sliders to 100%.

In SteamOS, open `Settings` goto `Audio` and you should see four new sound profiles.

> [!WARNING]
> You might get distortion at max volume!

> [!TIP]
> Enjoy!!!

## Unstable branch

> [!CAUTION]
> Installs the latest Manjaro updates, including KDE Plasma 6 and Mesa 1:24.0.3

### Switch to Unstable branch
```sh
sudo pacman-mirrors --api --set-branch unstable      
sudo pacman -Syu
```

> [!IMPORTANT]
> **Reboot**

## 6.9 amd kernel

> [!WARNING]
> This will install cutting edge 6.9 kernel *(it will take over an hour to compile and install!)*

> [!TIP]
> Worth it!

```sh
sudo yay -S linux-amd-drm-next
(press 2 then 4 for the two options)
```

> [!IMPORTANT]
> **Reboot**

Kernel version after updting `6.7.0-rc5-1-amd-drm-next-g5eabf0cd2673`.

<img width="960" alt="Screenshot_20240302_165615" src="https://github.com/ripplingsnake/Manjaro-SteamOS/assets/144014277/49c9ae42-ddb9-42aa-aef8-08c63910ec77">





