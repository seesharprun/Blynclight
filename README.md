 # Blynclight
Windows Universal portable library for the latest Blynclight device.

## Warning
> This is a very early alpha and will definitely not be up to my normal quality standard or tested thoroughly.  This project will evolve over time as more people wish to use a Blynclight with their Windows Universal app.

## Uses
This library uses the Windows Runtime HID libraries to communicate with the BlyncLight device.  This library has been tested with the following platforms:
- Windows Universal App running on Windows 10 preview
- Windows Universal App running on Raspberry Pi 2 with Windows 10 IoT

This library will soon be tested with the following platforms
- Windows Universal App running on Windows Phone
- Windows Universal App running on Xbox One
- Node.js Windows Universal App

## Getting Started
To get started, do the following three things:

1. Use the NuGet interface to import the **Blynclight** package.  

  > You can alternatively use the Package Manager Console with the following command ```Install-Package Blynclight -Pre```.

2. Add a declaration to your Universal App authorizing the device HID access.  This declaration should be added to the ```Capabilities``` element in your application's manifest file.
  
  ```xml
  <DeviceCapability Name="humaninterfacedevice">
    <Device Id="vidpid:0E53 2516">
      <Function Type="usage:FF00 0001"/>
    </Device>
  </DeviceCapability>
  ```
  
3. Add the following code anywhere in your application.

  ```C#
  var manager = new BlyncLight.Manager();
  await manager.Init();
  manager.BlyncLight.StatusColor = Colors.Blue;
  ```

## NuGet Package
[https://www.nuget.org/packages/Blynclight](https://www.nuget.org/packages/Blynclight)
