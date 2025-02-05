# The Sign
The Sign projects the glory of Purdue Hackers wherever there’s an outlet and an internet connection. A meter-tall, 3D printed and metal monument that shines out into the night.

## Key Information

- **Status**: Active
- **Maintainer**: [Jack](https://github.com/purduehackers/dark-forest/blob/main/people/organizers/imthesquid.md)

## Quick Links

- [Firmware Repo](https://github.com/purduehackers/sign-firmware)
- [Main Board Repo](https://github.com/purduehackers/sign-pcb)
- [ESP32 to Pico Repo](https://github.com/purduehackers/EspToPico)

## Troubleshooting

If the Sign doesn’t successfully turn on, turn it off and turn it back on after a few minutes.

‌**Boot Status Table**
- Red: Connecting to Wi-Fi
	- If the Sign reboots here ensure `PAL3.0` is available and the credentials on the Sign are assigned from a current student. Sometimes `PAL3.0` is flaky and you may need to wait a few minutes.
- Blue: Checking for updates
	- If the Sign reboots here something is wrong with the Github repo or they changed their API. Contact the maintainer.
- Green: Installing update
	- If the Sign reboots here it either is installing the update (fine) or it lost its connection (wait a few minutes).