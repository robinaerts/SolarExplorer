# Solar Explorer
![Solar Explorer](/solar/solarexplorer.webp)

Each year in Flanders a Solar Olympiad takes place. For an entire year selected students from Flemish schools work out an idea they have for a solar powered Race Car or a solar powered Gadget.

In 2023 we decided to participate in the challenge. We wanted to make a hybrid car that can both drive on land, as sail in water. We also wanted to put a camera on it, so we can remotely discover places where humans can't come.

### Selection process

Before we could start building our car, we had to pitch our idea to the solar team, because only a limited amount of people can actually start building it. For this we made a 3D prototype and a folder with a sketch of our idea in it.

[Our submission folder](/solar/inzending.pdf)
[3D prototype](https://solar-challenge-jo7b.vercel.app/")

### How it works

We had to make sure the car was as light as possible, and it was water tight. For that we used bearings for the holes where the wheels rotate, and silicon gel to make sure it's fully waterproof.

On the electronics part, we have an esp32 cam that works as the webserver. That's connected to the motor driver and the motors.
Then from your smartphone, you can connect to the local server and control it while viewing the path which it's going via the cameras.

### Finals

For the finals day on 17th May 2023 that took place in Technopolis. We brought our Solar Explorer fully finished. We also brought a small swimming pool to demonstrate the sailing capibilities.

After a stressfull pitch and demonstration, the jury members were impressed of our presentation, and at the end of the day we won the Pitch Price!

<img src="/solar/prize.jpg" alt="Pitch Prize"/>


## Building process

### Materials

- ESP32cam
- L298N Motor Driver
- 4 Motors of 12V each
- 4 Bearings
- Small Solar Panel
- Wood for the frame
- Plastic
- Silicon Gel

### The Frame

<img src="/solar/frame.jpg" alt="frame"/>

A car needs a strong skeleton, so the first step in building the solar car was creating a sturdy frame. It was made from a single wooden beam, chosen for its strength and lightness. The wood was cut into several angled pieces and glued together into a solid structure.

Once the frame was complete, durable plastic plates were attached to serve as the car’s casing, protecting the internal components. A silicone layer was added to the edges to ensure water resistance.

### Electrical Circuit

To function, the car requires an electrical circuit that meets key requirements:

- Remote control from any device (phone, tablet, computer)
- A built-in camera for live video feedback
- A solar-powered battery charging system

The circuit consists of three main components: the camera and controls, the motors, and the solar panel.

<img src="/solar/schema.jpg" alt="electrical schema"/>

For remote operation, an ESP32-CAM microcontroller was used due to its built-in camera, WiFi/Bluetooth connectivity, easy programmability, and affordability. The car's four 12V DC motors provide enough power for movement on land and water. A motor driver (L298N) ensures efficient power use, as the car is powered by two 4.2V Li-ion batteries.

A solar panel charges the batteries via a diode that prevents reverse current flow, protecting the panel. A multimeter was used to determine polarity before connecting it to the batteries. The circuit also includes two switches: one to control battery charging and another to turn the car on/off.

<img src="/solar/solarpanel.png" alt="solar panel connections"/>

The car is controlled digitally through a web application using JavaScript, which sends requests to a REST API. The ESP32 processes these requests, for example, to activate the motors. The API is programmed in C++, with the [code available on GitHub.](https://github.com/robinaerts/solarExplorer/)

### Water Propulsion

The Explorer is an amphibious vehicle, requiring movement on both land and water. It uses four-wheel drive on land, and instead of adding extra motors for water propulsion, the wheels were modified with paddle-like attachments.

Initially, the idea was to extend the wheel axles with rods and attach paddles, but this proved too fragile. Instead, the paddles were directly attached to the wheels.

<img src="/solar/peddels.png" alt="pedals"/>

To ensure water resistance, silicone was applied both inside and outside the car, sealing all gaps. The lightweight frame and large bottom surface contribute to the car’s buoyancy. The only internal components are the electrical circuit.

<br/>

[Read the full report (dutch)](https://robyte.robinaerts.be/publications/solar.pdf)
