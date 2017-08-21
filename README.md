# WiFiSCORE

WiFi signatures JSON database.

## Add an entry

To add a device entry, open a [Pull Request](https://github.com/berlin-open-wireless-lab/WiFiSCORE/pulls) with a new `device.json` placed in the right folder, *i.e.* in a folder named after the device's UUID in the corresponding category folder.

To generate the UUID, you can use this Python one-liner:

```
python3 -c "import uuid; print(str(uuid.uuid4()))"
```

## Entry format

| Field          	| Value                                                                                   	|
|----------------	|-----------------------------------------------------------------------------------------	|
| uuid           	| UUID version 4                                                                          	|
| name           	| Name of the device                                                                      	|
| categories     	| Array containing the device's category of the device and its parents in ascendant order 	|
| wifi_signature 	| WiFi signature                                                                          	|
| mac_vendor     	| Device's manufacturer as presented in Wireshark's OUI database                          	|
| created_at     	| Entry creation date - Python datetime.datetime                                          	|
| modified_at    	| Last modification time - Python datetime.datetime                                       	|
| image_url      	| UUID/PICTURE_SHA256.jpg                                                                 	|

`PICTURE_SHA256` means sha256 hash of the image file.

## Example

```
{
    "uuid": "8727be8a-b315-401d-acc3-e247785316be",
    "name": "Moto G4",
    "categories": [
        "Android",
        "Smartphone/Tablet/PDA"
    ],
    "wifi_signature": "wifi4|probe:0,1,50,...htmcs:000000ff",
    "mac_vendor": "Motorola",
    "created_at": "2017-06-29T14:28:53.981000Z",
    "modified_at": "2017-07-18T12:53:59.191000Z",
    "image_url": "8727...16be/6a02...r0qP.jpg"
}
```
