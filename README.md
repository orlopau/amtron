# Inofficial AMTRON API documentation

## Introduction

This repo contains a reverse-engineered documentation for the REST Api of a Mennekes Amtron 
EV-Charger equipped with Networking.

The information provided here was retrieved using the ChargeApp on Android and the Amtron Xtra 11 C2.

**It may not be applicable to other Amtron chargers.**

## Amtron API

### General Information

* The **DevKey required for each request** can be found in the documents you received with your Wallbox.
In the document it is called **APP-Pin**.
* Every request has to have the header param `Accept: application/json`.
* Every path shown below has a base url of `http://amtron-ip:25000/MHCP/1.0`
* Useful information can be found at the bottom of every page under **Notes**.

### Documentation

* [Get Device Information](./docs/api/DevInfo/get.md): `GET /DevInfo`
* [Set Device Information](./docs/api/DevInfo/post.md): `POST /DevInfo`
---
* [Get Charging Information](./docs/api/ChargeData/get.md): `GET /ChargeData`
* [Set Charging Information](./docs/api/ChargeData/post.md): `POST /ChargeData`
---
* [Set EnergyManager parameters](./docs/api/HomeManager/post.md): `POST /HomeManager`
