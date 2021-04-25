# harbora

> Harbora a is balabala.

<div style="align: center">
  <img src="https://user-images.githubusercontent.com/23714155/116004861-466ea300-a637-11eb-94c3-bc0c8b76f031.png">
</div>

## Whitepaper

### Abstract

### Home environment

#### Power device in line

- hard to move
- power supply all the time
- large power
- can connect by wire

#### Power device in battery

- easy to move
- small power
- energy saving required
- connect by wireless

### Leader Node

- device by wire as core node
- connect by wire first.
    - ethernet
    - PLC
- as wireless access point
- high performance
- distributed networking
- synchronize state from follower node
    - run multi replication zone
    - each zone need run BFT algorithm

### Follower Node

- power device by battery as follower
- connect by wireless first
    - WIFI
    - 6LowPAN
    - Bluetooth
- work at sleep mode
- low performance
- as data provide and command executor
- connect to core node

### State mapping and synchronize

- follow node connect a selected

### Core Network

### Future Work
