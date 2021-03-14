 
   
 

 
   
   
   
   
   
 

Papirus is a free and open source SVG icon theme for Linux, based on [Paper Icon Set](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e1f75f8c5e5a9f7e927111d5dc0aeabea94e2ec791e7c42ce6a8e365ce9653a9) with a lot of new icons and a few extras, like [Hardcode-Tray support](#hardcoded-tray-icons), [KDE colorscheme support](#kde-colorscheme), [Folder Color support](#folders-color), and [others](#extras).

Papirus icon theme is available in four variants:

 - Papirus
 - Papirus Dark
 - Papirus Light
 - ePapirus (for elementary OS and Pantheon Desktop)

## Contents

 - [Installation](#installation)
    - [Ubuntu and derivatives](#ubuntu-and-derivatives)
    - [Debian and derivatives](#debian-and-derivatives)
    - [Papirus Installer](#papirus-installer)
    - [Third-party packages](#third-party-packages)
 - [Hardcoded icons](#hardcoded-icons)
    - [Hardcoded application icons](#hardcoded-application-icons)
    - [Hardcoded tray icons](#hardcoded-tray-icons)
 - [KDE colorscheme](#kde-colorscheme)
 - [Folder's color](#folders-color)
 - [Extras](#extras)
 - [Recommendations](#recommendations)
 - [Manual fixes](#manual-fixes)
 - [Icon request](#icon-request)
 - [Contributing](#contributing)
 - [Donate](#donate)
 - [License](#license)

## Installation

### Ubuntu and derivatives

You can install Papirus from our official [PPA](http://u.720life.cn/g/50427b74640a5a0d7a20b955d81e1ca3819dfa1991c1706342220480b2cef4d99a45b26d42f929721a621edcb116a4005f52f763cc91fa7f221bba2e8221c71c):

```
sudo add-apt-repository ppa:papirus/papirus
sudo apt-get update
sudo apt-get install papirus-icon-theme
```

or download .deb packages from [here](http://u.720life.cn/g/50427b74640a5a0d7a20b955d81e1ca3819dfa1991c1706342220480b2cef4d99a45b26d42f929721a621edcb116a400b32e61a65604b10f6bcdd59d8fdaf99a7ba34da7e5df4a15ab3cd7194f479e3ce8a33e681335820350de7689d4a6a4197cf17384b11f9a6af39508a018945961).

**NOTE:** Now the daily builds of the papirus-icon-themes package are placed in [`ppa:papirus/papirus-dev`](http://u.720life.cn/g/50427b74640a5a0d7a20b955d81e1ca3819dfa1991c1706342220480b2cef4d99a45b26d42f929721a621edcb116a4008e19fbea4119a81a058c28acfdcf1f45).

### Debian and derivatives

Debian users also can install Papirus from our [PPA](http://u.720life.cn/g/50427b74640a5a0d7a20b955d81e1ca3819dfa1991c1706342220480b2cef4d99a45b26d42f929721a621edcb116a4005f52f763cc91fa7f221bba2e8221c71c), but the commands will differ:

```
sudo sh -c "echo 'deb http://ppa.launchpad.net/papirus/papirus/ubuntu bionic main' > /etc/apt/sources.list.d/papirus-ppa.list"

sudo apt-get install dirmngr
sudo apt-key adv --recv-keys --keyserver keyserver.ubuntu.com E58A9D36647CAE7F
sudo apt-get update
sudo apt-get install papirus-icon-theme
```

### Papirus Installer

Use the scripts to install the latest version directly from this repo (independently of your distro):

**NOTE:** Use the same script to update icon themes.

#### ROOT directory (recommended)

```
wget -qO- https://git.io/papirus-icon-theme-install | sh
```

#### HOME directory for GTK

```
wget -qO- https://git.io/papirus-icon-theme-install | DESTDIR="$HOME/.icons" sh
```

#### HOME directory for KDE

```
wget -qO- https://git.io/papirus-icon-theme-install | DESTDIR="$HOME/.local/share/icons" sh
```

#### \*BSD systems

```
wget -qO- https://git.io/papirus-icon-theme-install | env DESTDIR="/usr/local/share/icons" sh
```

#### Uninstall

```
wget -qO- https://git.io/papirus-icon-theme-uninstall | sh
```

### Third-party packages

Packages listed in this section are third-party packages. If you have a problem or a question, please contact the package maintainer.

Please note that some packages in the list may be outdated, open [Repology](http://u.720life.cn/g/0a6e5795735fd316ac3b31eac89c092fa2d552a127024f291b5770638019c713c8f7ed2281e72d978e51fd390faa7baca34b25f2d7efb21838c38c5b9c321bf6) to find out package versions.

| **Distro**    | **Maintainer**       | **Package**                              |
| :------------ | :------------------- | :--------------------------------------- |
| ALT Linux     | Andrey Cherepanov    | `apt-get install papirus-icon-theme`  [[link](http://u.720life.cn/g/ef290e076b81ef97791a042cd15959d471165bea41957afba6ec19b3a2f32b941732dcaee4d43b20cbeac690f2f1035bc48d1f9fc5a379de57dd4022b072eaf726c1f7db68571a8b2a5fb9ae727314ad)]  |
| Arch Linux    | Felix Yan            | `sudo pacman -S papirus-icon-theme`  community  |
| Arch Linux    | Mohammadreza Abdollahzadeh | [papirus-icon-theme-git](http://u.720life.cn/g/5615fdc361700551bb11c27e3ee88cb37d6b3406ae1ca466d10bbc6e99ffa776312ea00c58ad5f6b97ce768eabad2644f187b8df2a6efbd16ce790e039105a2d)  AUR  |
| Debian 9+     | Yangfl               | `sudo apt install papirus-icon-theme` |
| Fedora 27+    | Robert-André Mauchin | `sudo dnf install papirus-icon-theme` |
| Fedora        | Dirk Davidis         | [papirus-icon-theme](http://u.720life.cn/g/46da5b8c980a09c5eaf37dff8533a6983b7b0ed3eaf37f56aa6d45f0627f715b63a03076be448e9113dca6798daf69dba45c2e1e7e42db796d088895c4f3b0ca964e101111565ee4fab49a1d5322fd3e)  copr  |
| FreeBSD       | Hiroki Tagato        | [papirus-icon-theme](http://u.720life.cn/g/5487caf15af1e2fba214e3ddf0e95a2a2c520b2e8e4811c1daa5d56be24385ebd4fe8f7b5a6e9891d64bd7dd53148a1f44f6592e0fdf72facb189ded90537711)  freshports  |
| NetBSD        | Nia Alarie           | [papirus-icon-theme](http://u.720life.cn/g/19bc3cef89ecd809027325fa763bea13ef8f18e91a9dd39ea9e6d9c1e3a925174f11ecfd61e7459fac1c9080ef435f85)  pkgsrc  |
| NixOS         | Nixpkgs Contributors | `nix-env -iA nixos.papirus-icon-theme` |
| openSUSE      | Konstantin Voinov    | [papirus-icon-theme](http://u.720life.cn/g/5cf68d07a655cdcf94d83ccb5ed61446f5ab23cdb893aa9c218ffe485616b2b44bb828c444b5174eb8b7162744b00107a1810a54807a83bc3a1d74032001c2fa5f985df9b85e7aa7f4ab1ce8d2d0fa1ca01612b841e48cf58c5be0c7cb7de5ed)  OBS [[link](http://u.720life.cn/g/76ced8702eb890139a1d740b3805fe609fbec1b84d67c42fecdd10cdfed9bc9c08b673c187f389c752b26223c61804954737b257acd2062aeff2fc7ee48003493c02a33320d71315b02686b0600dcd91)]  |
| openSUSE      | Matthias Eliasson    | [papirus-icon-theme](http://u.720life.cn/g/5cf68d07a655cdcf94d83ccb5ed6144661edb7d8957810fc37b188c9d15f936e5e5ae233f8b7806a29df190c3ba075ad5efb4da685c992490eb5103057548212)  official  |
| ROSA Linux    | Vladimir Penchikov   | `sudo urpmi papirus-icon-theme` |
| Solus         | Joshua Strobl        | `sudo eopkg it papirus-icon-theme` |
| Ubuntu 18.04+ | Yangfl               | `sudo apt install papirus-icon-theme` |
| Void Linux    | Giuseppe Fierro      | `sudo xbps-install -S papirus-icon-theme` |

**NOTE:** If you are a maintainer and want to be in the list, please create an issue or make a pull request.

## Hardcoded icons

Some software uses an absolute path instead of the icon name in a .desktop file or in the source code which makes them unthemable.

### Hardcoded application icons

To deal with hardcoded application icons we recommend using [hardcode-fixer](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046559f92590a8cdb0981b550b57bc0054a492a7bca6be83489ee7eedbf331a9373). Papirus supports most of the applications in the [list](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046559f92590a8cdb0981b550b57bc0054ad48bcd8f3c1645f0255175607c9bd08127e874c548b06f518ab6abec5bc822debc7c27bd2b07bd9bb36d2072b79d5399). If [hardcode-fixer](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046559f92590a8cdb0981b550b57bc0054a492a7bca6be83489ee7eedbf331a9373) doesn't support your favorite app yet, please open an issue [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046559f92590a8cdb0981b550b57bc0054aca34e97276cd847344b88659b14c5f8a366a6a8fa72ba13314cf78a778efc3cb) or edit your .desktop file manually.

### Hardcoded tray icons

To fix hardcoded tray icons Papirus supports [Hardcode-Tray](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cef549633bb2a84e50e2e5291d79b03565145214020473a8e6bcb140ea1ab517) script. A list of supported applications is available [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cef549633bb2a84e50e2e5291d79b03565145214020473a8e6bcb140ea1ab517cd1ef46c618d071befc1e416ada5f70e6f64dde82c2236c5e5b0bf2d5bca89f8).

**NOTE:** To get Papirus to work right with Hardcode-Tray, use the hardcode-tray option `--conversion-tool RSVGConvert`:

```
sudo -E hardcode-tray --conversion-tool RSVGConvert --size 22 --theme Papirus
```

**Size recommendations:**

- Unity 22px
- KDE 22px
- GNOME 22px ([see](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a8d7b261ac4372f0b605d847fcaa1beb562ef146b671d149296d69551fedebf6e713abe9b33bead957a428f4a1c72db80e688c89e9a52f0b88810e5790aff5f8) for more info)
- XFCE 22px ([see](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a8d7b261ac4372f0b605d847fcaa1beb562ef146b671d149296d69551fedebf6e713abe9b33bead957a428f4a1c72db80e688c89e9a52f0b88810e5790aff5f8) for more info)
- Pantheon 24px
- Cinnamon 16px


![hardcode-tray](https://i.imgur.com/6hFm6aj.png)

**NOTE**: Some Electron-based applications have blurred tray icon on KDE (see [bug report](http://u.720life.cn/g/80a402ad3d54680820d2e18910e6719e72e22d8a2fce02446efa08e7ce2db896171c49180aa466c5dc8dfc4481868b12) To solve this issue pass the following environment variable to the app: `XDG_CURRENT_DESKTOP=Unity wire-desktop`

## KDE colorscheme

Support for monochrome icons for KDE colorscheme is now available:
- Papirus - for dark plasma theme & light color scheme
- Papirus Dark - for dark plasma theme & color scheme
- Papirus Light - for light plasma theme & color scheme

![kde-color-scheme](https://i.imgur.com/oM1qhQH.png)

**NOTE:** Non-KDE apps don't support KDE colorscheme on the system tray, but you can replace color manually.

## Folder's color

Papirus has [Folder Color](http://u.720life.cn/g/d0cc3f7b9e277117784cd90f6e44f043dcea6e68909b3500a7c9dce05e8a722c77066970891e7f08e1a1317c1ccb536f) v0.0.80+ support that allows you to change a color of a folder.

Available colors:

![Folder Color Preview](https://i.imgur.com/jP3mRci.png)

For KDE, colors of individual folders can be changed using [dolphin-folder-color](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c1c619f262fa204b289b3692b24e77f8d26ada2428429b3013ac74ef1507a397).

Also, you can use our [papirus-folders](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a8d7b261ac4372f0b605d847fcaa1beb562ef146b671d149296d69551fedebf66c1b8b346c8f53094e443cff421f9a38) script to apply the color of folders system-wide.

## Extras

- [Papirus theme for LibreOffice](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a8d7b261ac4372f0b605d847fcaa1beb562ef146b671d149296d69551fedebf62d1c172e29c5a264651e9ee86ba6df4d7b78f37a03d4cce77fd8b0c7610ad948)
- [Papirus themes for FileZilla](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a8d7b261ac4372f0b605d847fcaa1beb562ef146b671d149296d69551fedebf6054381bc553a3151c849cc1ee94bbeaae4e0a77920b6fa0f3c9f032da5cf42dc)
- [Papirus theme for SMPlayer](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a8d7b261ac4372f0b605d847fcaa1beb562ef146b671d149296d69551fedebf67159ae31fcb0b913d74263a539539234)
- [Papirus themes for Claws Mail](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a8d7b261ac4372f0b605d847fcaa1beb562ef146b671d149296d69551fedebf61c775ca9aff44c1953f8c0b9b71e70d41d83ea768dff0880f0b6118783920e23)
- [Papirus themes for Thunderbird](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a8d7b261ac4372f0b605d847fcaa1beb10abed2f20ad154e04d00513d5247aa9f495ba75e8a1b4a46c489be9e899a3759a5178f39656934f24f95bca780a5d31)
- [Papirus theme for aMule](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a8d7b261ac4372f0b605d847fcaa1beb562ef146b671d149296d69551fedebf66300b3048c3a28534b0de3e620172776)

## Recommendations

- Recommended use Papirus icons alongside one of the following GTK themes:
  - [Adapta theme](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469aa0ad79b55823351c65369ed30516804f3f054a2d276e77f25b649b38eb3f1ba3bd6fd5d42e835d4da6f5baf75ba3a7)
  - [Arc theme](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046146c4b76d7aa668d5375222418cf582b516d632227afea283d5c52d9a4c50747)
  - [Materia theme](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466c9c47e0e27081f4c541813e7cfa5f110218203465c667353b5c99603abc60de)
- For KDE, our recommendation is:
  - [Adapta KDE](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a8d7b261ac4372f0b605d847fcaa1bebbd4bf75ff0b7c09ab9fa43bfc2854f1b0e1546832878361767463731a29624fb)
  - [Arc KDE](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a8d7b261ac4372f0b605d847fcaa1bebf6c93382027ce4cea2d84b8a55e028e8fa2dd850e2c744bea8449fd5110913f3)
  - [Materia KDE](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a8d7b261ac4372f0b605d847fcaa1bebe84e571efacca89ab7d09048a880245cbe391081837ee891e586d2137543559c)

## Manual fixes

 
 For Cinnamon users 

For Cinnamon users who want to use Papirus icon theme with [Arc theme](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046146c4b76d7aa668d5375222418cf582b516d632227afea283d5c52d9a4c50747) we recommend fix color icons on panel:

```
sudo sed -i.orig 's/white/#d3dae3/g' /usr/share/themes/Arc-Dark/cinnamon/cinnamon.css
```

![Cinnamon Arc-Dark theme fix](https://i.imgur.com/XXejgtD.png)

To deal with blurred panel icons, increase the panel size up to 30px in `Systems Settings` → `Panel` (see [screenshot](http://u.720life.cn/g/53e32d7e258402cc75ba14d3d6fa961dee2f7d62207edfe61745f2987af7d031)
 

 
 For GNOME Shell users 

For GNOME users we recommend install the following extensions:

- [(K)StatusNotifierItem/AppIndicator Support](http://u.720life.cn/g/274e01494146acb396dd112078beec5e63af94006b05fd1740f36f5b07c22ec95c7938563d6a3d9928e4b4dd37f3b838f96aa99aab0d5967b5021798b720b6e1) **¹** — This extension integrates AppIndicators. The patched version of [sni-qt](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f7375ed0474244bacaa0aa83e531696fa6200bdafb93487936c27f358c2de22e) for [Hardcode-Tray](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f7375ed0474244bacaa0aa83e531696f36beafc853e257a1a6fa5531b6398c62) doesn't work without it.
- [Dash to Dock](http://u.720life.cn/g/274e01494146acb396dd112078beec5e63af94006b05fd1740f36f5b07c22ec93d54d6083dabb79e5f750f23648be7cfae14284a7ddec24aa7b64f0cf73757f1) **¹**
- [No Symbolic Icons](http://u.720life.cn/g/274e01494146acb396dd112078beec5e63af94006b05fd1740f36f5b07c22ec9b1128f3e6f6111d3037785e08dcf676da13ab2d34813194ba2b5982289d429a0)
- [Status Area Horizontal Spacing](http://u.720life.cn/g/274e01494146acb396dd112078beec5e63af94006b05fd1740f36f5b07c22ec955c72da87addbec1552f029e7b148860426e4f096dd09b38716941e22dd1c35d84eadb67ca0af3257505a7382cbe5ab7)

**¹** On Ubuntu 18.04+ it is pre-installed.
 

 
 For Xfce users 

Here are a few recommendations for Xfce users.

#### Thunar File Manager

Go to `Edit` → `Preferences...`. Click on `Side Pane` tab. Under `Side Pane`, look for `Icon Size` and set to `Very Small`.

![thunar-prefecences](https://i.imgur.com/Iu1TIEa.png)

#### Notification Area

Go to `Settings Manager` → `Panel` → `Items` tab. Select `Notification Area` item and click on `Edit currently selected item` button. Under `Appearance` set the following options:

- Set `Maximum icon size (px)` to `24`
- Uncheck `Show frame`

![xfce4-notification-area](https://i.imgur.com/MopCZBZ.png)
 

 
 For elementary/Pantheon users 

With light wallpaper, we recommend disable `use-transparency` option on wingpanel:

```
gsettings set org.pantheon.desktop.wingpanel use-transparency false
```

 

## Icon request

- Application name
- Icon name (see desktop-file option **Icon** on `/usr/share/applications`)
- Original icon image
- Small description and/or a link to the official webpage

**NOTE**: We do NOT support Windows/Wine/Crossover or other NOT native Linux-apps. This also applies to discontinued projects!!

## Contributing

We welcome user contributions. If you don't know where to start, we've compiled a list of things we would like to see in your pull request:

- new icons for missing applications
- symbolic links to an existing icon
- resolving open issues
- spelling, grammar, phrasing
- improvements to our scripts

Inside [tools/work](tools/work) you will find a step-by-step guide, an environment, and tools that will help you:

- [create a new icon](tools/work#create-a-new-icon) from template
- [make a symlink to an existing icon](tools/work#make-symlinks-to-an-existing-icon)
- [edit an existing icon](tools/work#edit-an-existing-icon)
- convert your icon to all variants of the theme

We are waiting for your pull requests and would love to see this icon theme become as complete as possible.

## Donate

You can support this open source project by making a voluntary payment:

- Patreon: https://www.patreon.com/varlesh
- PayPal: https://www.paypal.me/varlesh

## License

Papirus icon theme distributed under the terms of the GNU General Public License, version 3. See the [`LICENSE`](LICENSE) file for details.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed149e17ac78f6ed15960f1535cc30bdaddf61872a74b723f17f4181dd1004ef02d86a12f2c6d31deb717eda36e4f27e699f78116d7d683f11ca8fb75c5b5d893)