<p align="center">
  <a href="#build-framework">
   <img src="https://raw.githubusercontent.com/armbian/build/master/.github/armbian-logo.png" alt="Armbian logo" width="144">
  </a><br>
  <strong>Armbian OS</strong><br>
<br>
<a href=https://github.com/armbian/os/actions/workflows/complete-artifact-matrix-all.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/complete-artifact-matrix-all.yml?logo=githubactions&label=Artifacts&style=for-the-badge&branch=main"></a> <a href=https://github.com/armbian/os/actions/workflows/repository-update.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/repository-update.yml?logo=githubactions&label=Repository&style=for-the-badge&branch=main"></a> <a href=https://github.com/armbian/os/actions/workflows/full-distro-build-and-test.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/full-distro-build-and-test.yml?logo=githubactions&label=Deboostrap&style=for-the-badge&branch=main"></a> <a href=https://github.com/armbian/os#latest-smoke-tests-results><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/smoke-tests.yml?logo=githubactions&label=Smoke%20tests&style=for-the-badge&branch=main"></a>
</p>


## What does this project do?

- Builds quarterly [stable](https://www.armbian.com/download/), daily [rolling](https://github.com/armbian/os/releases/latest) and weekly [community](https://github.com/armbian/community/releases/latest) Armbian OS images
- Keeps build framework [packages artifacts](https://github.com/orgs/armbian/packages) cache up to date to secure fast rebuild process
- Keeps stable [apt.armbian.com](https://apt.armbian.com) and nightly [beta.armbian.com](https://beta.armbian.com) packages repository up to date
- Keep synchronizing the selection of [3rd party](external) applications with Armbian repositories
- Reversion Firefox, Thunderbird and Chromium to higher (9) epoch version then its Snapd counterparts (1)
- Tests install of all packages added onto stable and testing Debian and Ubuntu releases
- Tests packages upgrade sucess on real hardware
- Tests build [supported and community supported desktops](https://github.com/armbian/os/actions/workflows/full-distro-build-and-test.yml)

## How to enable images?

Build lists are generated [automatic](https://github.com/armbian/os/blob/main/.github/workflows/recreate-matrix.yml#L59-L211C94) based on [support policy](https://docs.armbian.com/User-Guide_Board-Support-Rules/) and with help of [templates](userpatches/), .blacklist and .map files.

## When is this happening?

- Artifacts cache is updated every eight hours, starting at 0:00 AM UTC
- Repository update starts after artifacts cache update is done succesfully
- Smoke tests starts once per day at 5:30 AM UTC
- Nightly images are build once per day, at 2:00 AM UTC, or if [build config / template is changed](https://github.com/armbian/os/blob/main/userpatches/targets-release-nightly.yaml)
- Manually, when Armbian [release manager](https://github.com/orgs/armbian/teams/release-manager) executes a build action

## Latest smoke tests results:

- installs **kernels**, **device tree blob** and **headers**
- runs **network** (iperf) and **computing performance** tests (7z benchmark)
- store **armbianmonitor** logs

<!--START_SECTION:data-section-->
<table width="100%"><tr><td align="left"><a id=Board ID href=#Board ID><b>Board name</b></a></td><td align=center><b>Kernel version</b></td><td align=center><b>Support</b></td><td align=left><b>Logs</b></td><td align=right><b>Iperf</b></td><td align=right><b>7z -b</b></td><td align=right><b>Repo</b></td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=center>6.6.38-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uyivuhocaq><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>97</td><td align=right>3719</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=center>6.9.8-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ilapapadux><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>3722</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=center>6.6.36-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/owakenodiw><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>805</td><td align=right>2608</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=center>6.7.12-edge-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/eciwupitar><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>809</td><td align=right>2453</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpi-e href=#rockpi-e>Rockpi E</a></td><td align=center>6.6.38-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uwaxolakoh><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>3300</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpi-e href=#rockpi-e>Rockpi E</a></td><td align=center>6.9.8-edge-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/cuniposiki><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>2985</td><td align=right>beta</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=center>6.6.36-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/qecokaviya><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>860</td><td align=right>3953</td><td align=right>beta</td></tr><tr><td align="left"><a id=lime-a64 href=#lime-a64>A64 OLinuXino</a></td><td align=center>6.6.36-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/oleqahunik><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>882</td><td align=right>2650</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.6.37-current-bcm2711</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ruxudotelo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>791</td><td align=right>5807</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.9.8-edge-bcm2711</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/edeyujijoj><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>860</td><td align=right>5774</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=center>6.6.38-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/imayatapiy><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>3449</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=center>6.9.8-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/kukomujibo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>91</td><td align=right>3426</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=center>6.6.38-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=#><img src=https://img.shields.io/static/v1?label=&message=N/A&color=white></a></td><td align=right>890</td><td align=right>3808</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=center>6.9.8-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=#><img src=https://img.shields.io/static/v1?label=&message=N/A&color=white></a></td><td align=right>780</td><td align=right>3489</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=center>6.6.38-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/obiwahuyat><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>761</td><td align=right>6202</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=center>6.9.8-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ipehotajat><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>826</td><td align=right>6179</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=center>6.6.38-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/sanetucuqa><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>740</td><td align=right>6996</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=center>6.9.8-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ovupepeyov><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>7147</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopim4 href=#nanopim4>NanoPi M4</a></td><td align=center>6.6.38-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/xucuwegile><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>6718</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=center>6.6.38-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/uruyemutax><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>520</td><td align=right>5625</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=center>6.9.8-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/camujupaci><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>887</td><td align=right>5647</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.6.37-current-bcm2711</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/osamabogoy><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>2299</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.9.8-edge-bcm2711</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/egacipanak><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>2247</td><td align=right>beta</td></tr><tr><td align="left"><a id=cubietruck href=#cubietruck>Cubietruck</a></td><td align=center>6.6.36-current-sunxi</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/odayopireh><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>343</td><td align=right>1015</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2ultra href=#bananapim2ultra>Banana Pi M2 Ultra</a></td><td align=center>6.6.36-current-sunxi</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/obehomivuq><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>709</td><td align=right>2721</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5-plus href=#orangepi5-plus>Orange Pi 5 Plus</a></td><td align=center>6.1.43-vendor-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/apacaricol><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>114</td><td align=right>18441</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepioneplus href=#orangepioneplus>Orange Pi One+</a></td><td align=center>6.6.36-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/juvilayoju><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>704</td><td align=right>3949</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=center>6.6.38-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/rawohemore><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>848</td><td align=right>8973</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=center>6.9.8-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/olotimajeq><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>780</td><td align=right>8814</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-edge2 href=#khadas-edge2>Khadas Edge2</a></td><td align=center>6.1.43-vendor-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ozeriyayok><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>18807</td><td align=right>beta</td></tr><tr><td align="left"><a id=tinkerboard-2 href=#tinkerboard-2>Tinker Board 2</a></td><td align=center>6.6.38-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/keyexufehu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>860</td><td align=right>6893</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2pro href=#bananapim2pro>Banana Pi M2Pro</a></td><td align=center>6.6.38-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/oguxiyituj><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>5317</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2pro href=#bananapim2pro>Banana Pi M2Pro</a></td><td align=center>6.9.8-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uqenahimov><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>550</td><td align=right>5320</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim4 href=#khadas-vim4>Khadas VIM4</a></td><td align=center>5.15.119-legacy-meson-s4t7</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/wegidubuli><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>176</td><td align=right>11572</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>Odroid M1</a></td><td align=center>6.6.38-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ovurixamam><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>449</td><td align=right>5180</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>Odroid M1</a></td><td align=center>6.9.8-edge-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/okicebiroh><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>490</td><td align=right>5178</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero href=#orangepizero>Orange Pi Zero</a></td><td align=center>6.6.36-current-sunxi</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/eyucufakat><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>2935</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=center>6.4.13-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>8905</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=center>6.4.13-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>887</td><td align=right>8820</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r4s href=#nanopi-r4s>NanoPi R4S</a></td><td align=center>6.6.38-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uyobekiguw><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>6518</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5 href=#orangepi5>Orange Pi 5</a></td><td align=center>6.1.43-vendor-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/asaputotig><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>213</td><td align=right>18957</td><td align=right>beta</td></tr><tr><td align="left"><a id=udoo href=#udoo>Udoo</a></td><td align=center>6.6.38-current-imx6</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/jixekarife><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>388</td><td align=right>2378</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero2 href=#orangepizero2>Orange Pi Zero2</a></td><td align=center>6.6.36-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Staging&color=orange></a></td><td align=left><a href=https://paste.armbian.com/ulimoqewus><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>547</td><td align=right>2347</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepilite2 href=#orangepilite2>Orange Pi Lite 2</a></td><td align=center>6.6.36-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/etutisanaf><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>3635</td><td align=right>beta</td></tr></table>
<!--END_SECTION:data-section-->

## Would you like to join spare hardware to this automated testings?

All you need to do is:

- deploy any latest Armbian image to hardware
- provide IP address
- [contact us](https://www.armbian.com/contact/)

Device has to be always on and easily accesible for you to re-image in case of failed upgrade.

## Development

- [Pull request](https://github.com/armbian/build/pulls)
- [Weekly developers meetings](https://forum.armbian.com/events/)
- [Forums for developers](https://forum.armbian.com/forum/4-advanced-users-development/)

## Download prebuilt images

- [quarterly released **standard support** builds](https://www.armbian.com/download/?device_support=Standard%20support)
- [automatic released **rolling release** builds](https://github.com/armbian/os/releases/latest) (daily or when code changes)
- [weekly released **community maintained** builds](https://github.com/armbian/community/releases/latest)

## Support

- [Using Armbian](https://forum.armbian.com/forum/23-using-armbian/)

## Contact

- [Forums](https://forum.armbian.com) for Participate in Armbian
- IRC: `#armbian` on Libera.chat
- Discord: [https://discord.gg/armbian](https://discord.gg/armbian)
- Follow [@armbian](https://twitter.com/armbian) on X (formerly known as Twitter), [Fosstodon](https://fosstodon.org/@armbian) or [LinkedIn](https://www.linkedin.com/company/armbian).
- Bugs: [issues](https://github.com/armbian/build/issues) / [JIRA](https://armbian.atlassian.net/jira/dashboards/10000)
- Office hours: [Wednesday, 12 midday, 18 afternoon, CET](https://calendly.com/armbian/office-hours)
