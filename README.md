# Vehicle Tracking System

A real-time vehicle tracking system using Arduino, GPS, and GSM modules. Send an SMS with "LOCATION" to get the current GPS coordinates as a Google Maps link.

## Features

- 📍 Real-time GPS location tracking
- 📱 SMS-based location requests
- 🗺️ Google Maps integration for easy location viewing
- 🔧 Simple Arduino-based hardware setup
- ⚡ Low power consumption

## Hardware Requirements

- Arduino Uno or compatible board
- GPS Module (Neo-6M or similar)
- GSM Module (SIM800L or SIM900A)
- SIM card with SMS capability
- Jumper wires
- Breadboard or PCB
- Power supply (7-12V for Arduino)

## Wiring Diagram

### GPS Module Connections
- GPS VCC → Arduino 5V
- GPS GND → Arduino GND
- GPS TX → Arduino Pin 4 (RX)
- GPS RX → Arduino Pin 3 (TX)

### GSM Module Connections
- GSM VCC → Arduino 5V (or external 3.7-4.2V)
- GSM GND → Arduino GND
- GSM TX → Arduino Pin 9 (RX)
- GSM RX → Arduino Pin 10 (TX)

## Software Dependencies

- **TinyGPS++** library by Mikal Hart
- **SoftwareSerial** library (included with Arduino IDE)

### Installing Libraries

1. Open Arduino IDE
2. Go to **Sketch → Include Library → Manage Libraries**
3. Search for "TinyGPS++" and install the latest version

## Setup Instructions

1. **Clone or download this repository**
2. **Open the Arduino IDE** and load the `.ino` file
3. **Update the phone number** in the code:
   ```cpp
   String phoneNumber = "+1234567890";  // Replace with your phone number
   ```
4. **Upload the code** to your Arduino board
5. **Insert a SIM card** into the GSM module
6. **Power on the system** and wait for GPS lock

## Usage

1. **Power on the device** and wait for initialization
2. **Send an SMS** with the text "LOCATION" to the SIM card number
3. **Receive GPS coordinates** as a Google Maps link via SMS
4. **Click the link** to view the exact location on Google Maps

### Example SMS Response
```
Your Location: https://maps.google.com/?q=40.748817,-73.985428
```

## Code Structure

- **setup()**: Initializes serial communications and GSM module
- **loop()**: Continuously reads GPS data and processes incoming SMS
- **sendMapLink()**: Sends GPS coordinates as Google Maps URL via SMS

## Troubleshooting

### GPS Issues
- Ensure GPS module has clear sky view
- Wait 2-5 minutes for initial GPS lock
- Check wiring connections

### GSM Issues
- Verify SIM card is properly inserted and activated
- Check network signal strength
- Ensure sufficient power supply for GSM module

### General Issues
- Monitor Serial output at 9600 baud for debugging
- Check all wiring connections
- Verify library installations

## Power Considerations

- GSM modules require significant power during transmission
- Consider using external power supply for GSM module
- Add capacitors to stabilize power during SMS transmission

## Future Enhancements

- [ ] Battery level monitoring
- [ ] Geofencing alerts
- [ ] Multiple phone number support
- [ ] Speed and direction tracking
- [ ] Data logging to SD card
- [ ] Web interface for tracking

## Safety and Legal Notes

- Ensure compliance with local regulations for vehicle tracking
- Respect privacy laws when tracking vehicles
- Use only for authorized vehicles
- Consider data security and encryption for sensitive applications

## License

This project is open source. Feel free to modify and distribute according to your needs.

## Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.

## Support

For questions or issues, please open a GitHub issue or contact the maintainer.
