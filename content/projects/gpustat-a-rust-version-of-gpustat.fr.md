---
title: "gpustat : une version Rust de gpustat."
date: 2021-08-28T15:00:30.183Z
extra:
  link: https://crates.io/crates/gpustat
  image: /media/rust-logo-blk.svg
description: 📊 Un utilitaire en ligne de commande simple pour interroger et surveiller l'état des GPU
taxonomies:
  tags:
    - Rust
    - GPU
    - Nvidia
---
### gpustat

[![Crates.io](https://img.shields.io/crates/v/gpustat.svg)](https://crates.io/crates/gpustat)
[![license](https://img.shields.io/github/license/alongwy/gpustat.svg?maxAge=86400)](LICENSE)

Une version Rust de [gpustat](https://github.com/wookayin/gpustat).

Juste *moins* que nvidia-smi ?

#### Utilisation

`$ gpustat`

Options :

* `--color`            : Forcer la sortie colorée (même quand stdout n'est pas un tty)
* `--no-color`         : Supprimer la sortie colorée
* `-u`, `--show-user`  : Afficher le nom d'utilisateur du propriétaire du processus
* `-c`, `--show-cmd`   : Afficher le nom du processus
* `-f`, `--show-full-cmd`   : Afficher la commande complète et les statistiques CPU du processus en cours
* `-p`, `--show-pid`   : Afficher le PID du processus
* `-F`, `--show-fan`   : Afficher la vitesse du ventilateur du GPU
* `-e`, `--show-codec` : Afficher l'utilisation de l'encodeur et/ou du décodeur
* `-a`, `--show-all`   : Afficher toutes les propriétés ci-dessus

#### Installation rapide

Installation depuis Cargo :

```
cargo install gpustat
```

#### Affichage par défaut

> [0] | A100-PCIE-40GB | 65'C | 75 % | 33409 / 40536 MB | along(33407M)

- `[0]` : index GPU (commence à 0) en tant que PCI_BUS_ID
- `A100-PCIE-40GB` : nom du GPU
- `65'C` : température
- `75 %` : taux d'utilisation
- `33409 / 40536 MB` : utilisation de la mémoire GPU
- `along(33407M)` : nom d'utilisateur des processus en cours sur le GPU (et leur consommation mémoire)

#### Licence

[Licence GPL v2](LICENSE)
