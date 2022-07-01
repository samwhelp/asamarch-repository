# asamarch-repository

* [asamarch-repository](https://samwhelp.github.io/asamarch-repository/) ([GitHub](https://github.com/samwhelp/asamarch-repository))
* [asamarch-packaging](https://github.com/samwhelp/asamarch-packaging)


## Use Remote

* /etc/pacman.conf

``` ini
[asamos]
SigLevel = Optional TrustAll
Server = https://samwhelp.github.io/asamarch-repository/repo/main
```

run

``` sh
sudo pacman -Sy
```

run

``` sh
sudo pacman -S asamos-hello
```


## Use Local

run to clone

``` sh
sudo mkdir -p /opt/asamos/
sudo chmod 777 /opt/asamos/
git clone https://github.com/samwhelp/asamarch-repository.git /opt/asamos/asamarch-repository
```


* /etc/pacman.conf

``` ini
[asamos]
SigLevel = Optional TrustAll
Server = file:///opt/asamos/asamarch-repository/repo/main
```


run

``` sh
sudo pacman -Sy
```

run

``` sh
sudo pacman -S asamos-hello
```


## Use Include

* [/etc/pacman.d/asamos-mirrorlist](https://github.com/samwhelp/asamarch-packaging/blob/main/pack/base/asamos-mirrorlist/asset/etc/pacman.d/asamos-mirrorlist)

```
#Server = file:///opt/asamos/asamarch-repository/repo/main
Server = https://samwhelp.github.io/asamarch-repository/repo/main
```

* /etc/pacman.conf

``` ini
[asamos]
SigLevel = Optional TrustAll
Include = /etc/pacman.d/asamos-mirrorlist
#Server = file:///opt/asamos/asamarch-repository/repo/main
#Server = https://samwhelp.github.io/asamarch-repository/repo/main
```

run

``` sh
sudo pacman -Sy
```

run

``` sh
sudo pacman -S asamos-hello
```
