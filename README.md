# Browser Block Demo

<img src="web.jpg">

This project is a ready-to-deploy example of the [balena browser block](https://github.com/balena-labs-projects/browser).

The browser block provides a hardware accelerated web browser to present internal and external URLs on a connected display. The browser block is a docker image that runs a Chromium browser via X11, optimized for balenaOS. This project runs on Raspberry Pi 3, 4, 5, Zero 2W, and amd64.

## Deploy this project

Simply click the button below. If you don't already have a [balenaCloud](https://www.balena.io/) account you'll be asked to create one. (BalenaCloud is a remote device management platform and the first ten devices are free and full-featured. No credit card required!)

[![balena deploy button](https://www.balena.io/deploy.svg)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/cjs59/browser-block-demo)

Follow the instructions for downloading the image and flashing an SD card. Boot your device with the SD card inserted.

## Usage

Make sure your device is connected to the internet and the SD card/flash media is inserted. Also make sure a monitor is connected to your device so you can view the web browser display. Power on your device and after the software has been downloaded you should see the welcome web page on your monitor.

<img src="screen.png">

Configure the displayed URL by setting a [variable](https://docs.balena.io/learn/manage/variables/) on the balenaCloud dashboard:

- On the balenaCloud dashboard, make sure you are viewing your device summary page by clicking on a device
- Click on "variables" on the left side menu the "Add variable"
- In the "Add variable" dialog box, type `LAUNCH_URL` in the "Name" text box and type the URL you want to display in the "Value" box.
- Click the "Add"button, then click the "Apply all changes" button.
- You containers will restart and the new URL should be displayed on the device's monitor.

You can repeat the above steps to change the URL displayed on any of the devices in your fleet. If you want to change all of the devices to the same URL at once, you can use the [fleet-level variable](https://docs.balena.io/learn/manage/variables/#fleet-wide-variables) feature.

## Customize

There are many variables you can set in the browser block to change the appearance and behavior of the browser. See the [browser block documentation](https://github.com/balena-labs-projects/browser?tab=readme-ov-file#environment-variables) for a list of all the variables. For the best results with digital signage applications, you may want to set the `KIOSK` variable to `1`.

## Troubleshooting

If the video is disorted or the screen is blank, you may need to increase the GPU memory on the device. For a Raspberry Pi, go to the "Device configuration" menu item on the left of the dashboard and set the "Define device GPU memory in megabytes" value to 64 or 96.

## Deploy a fleet of these devices

BalenaCloud is all about making it easy to maintain fleets of devices. To easily add more device, simply flash the same image used for the first device to additional SD cards and boot additional devices. They will all get their own unique ID and show up as separate devices in your dashboard. You can then remotely change the displayed URL using the steps described above. 


Photo by <a href="https://unsplash.com/@artnok?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Nicolas Picard</a> on <a href="https://unsplash.com/photos/selective-focus-photography-of-spiderweb--lp8sTmF9HA?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
  
