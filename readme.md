# Makerfabs nRF52840 UWB DW3000

**The DW3000 library in this repository was developed by NConcepts, not Makerfabs.  Makerfabs is simply responsible for maintaining the repository.**

## 1.Intruduce

Product Link ：[nRF52840 UWB DW3000]() 

Wiki Link : [nRF52840 UWB DW3000](https://wiki.makerfabs.com/nRF52840%20DW3000%20UWB.html)

Usage : [one-anchor--one-tag](https://github.com/Makerfabs/nRF52840-UWB-DW3000#31-one-anchor--one-tag)

[multi-anchor--multi-tag](https://github.com/Makerfabs/nRF52840-UWB-DW3000#32-multi-anchor--multi-tag)

## 2.Feature

- Controller: nRF52840, 64 MHz Cortex-M4 with FPU, 1 MB Flash, 256 KB RAM.
- DW3000 UWB module.

## 3. Usage

Download the DW3000 library in [GitHub](https://github.com/Makerfabs/nRF52840-UWB-DW3000/tree/main/Dw3000), and put it to the Arduino library file.

- The default is usually in the "C:\Users\Your username\Documents\Arduino\libraries"

![lib.png](https://wikiadmin.makerfabs.com/api/uploads/images/490f0d7d20e1411398f9fea3145ecbde.png)

### 3.1 One Anchor + one Tag

- Prepare the module and connect it to the PC with a USB cable.

- Open the Arduino IDE.

- Click **File-->Examples-->DW3000-->Makerfabs_Range_TX**.

![range_tx.png](https://wikiadmin.makerfabs.com/api/uploads/images/c9e818219e974642881ab86ae0f246c0.png)

- Select the development board “Nordic nRF52840 DK” and the port.

![Nordic nRF52840 DK.png](https://wikiadmin.makerfabs.com/api/uploads/images/411a75d63fbd43f1902aa3de819ad8b9.png)

- Upload the sketch to the board.

![IMG20260815163745.jpg](https://wikiadmin.makerfabs.com/api/uploads/images/cc14952609cf4b759e9042f083e0eaab.jpg)

- Prepare **another module** and connect it to the PC with a USB cable.

- Click **File-->Examples-->DW3000-->Makerfabs_Range_RX**.

![range_rx.png](https://wikiadmin.makerfabs.com/api/uploads/images/f82c6113c0944df4bba90264d2d3945d.png)

- Select the development board “Nordic nRF52840 DK” and the port.

- Upload the sketch to the board.

![IMG20260815114207.jpg](https://wikiadmin.makerfabs.com/api/uploads/images/39c0a29ed8794070b237702b5281643c.jpg)


### 3.2 Multi Anchor + Multi Tag

This is the example to get the distance value from multi Tag to multi Anchor.

The network uses a designated **Master Anchor** to coordinate synchronization and network scheduling.

``` 
#define MASTER_ANCHOR_ID    0xA0
```

The Master Anchor serves as the reference node for the entire UWB network and is responsible for:

- TDMA timing coordination
- Tag scheduling reference
- Maintaining a common network time base

All Anchors and Tags in the network must be configured with the same `MASTER_ANCHOR_ID`.


**Set the board to Anchor X or Tag X**

- Open the Arduino IDE.

- Click **File-->Examples-->DW3000-->Makerfabs_Multi_Anchor_Multi_Tag_Anchor** to open the Anchor code.

![A.png](https://wikiadmin.makerfabs.com/api/uploads/images/5c530206336342608c56b20ed892c1f0.png)

- Click **File-->Examples-->DW3000-->Makerfabs_Multi_Anchor_Multi_Tag_Tag** to open the Tag code.

![T.png](https://wikiadmin.makerfabs.com/api/uploads/images/7a4ebb5334bd4906bc11b33adcf8ae3e.png)

Modify code to get the Anchor or Tag that you want to define

``` 
// 0xA0~0xA7
#define MASTER_ANCHOR_ID    0xA0
```

``` 
//For example 0, 1, 2..
#define TAG_ID              0
```

Use Type-C USB cable to connect the board and PC, and select the development board "Nordic nRF52840 DK" and the port.

![Nordic nRF52840 DK.png](https://wikiadmin.makerfabs.com/api/uploads/images/411a75d63fbd43f1902aa3de819ad8b9.png)

Verify the code and upload.

Repeat to set up multiple Anchor and multiple Tag.

Open the port for any anchor to view the distances from all tags to all anchors.

![result2_2.png](https://wikiadmin.makerfabs.com/api/uploads/images/35a17f3794574cf888322e5c32256631.png)

Results for 8Tag + 8anchor
![result8_8_.png](https://wikiadmin.makerfabs.com/api/uploads/images/c6f114ffacf54f74893c60b22bce32f5.png)

### 3.3UWB Positioning Python Program
You can use Python for UWB positioning. Double-click to open [uwb_visualizer.exe](https://github.com/Makerfabs/Makerfabs-ESP32-UWB-DW3000/tree/main/example/uwb_visualizer).

![uwb_visualizer.png](https://wikiadmin.makerfabs.com/api/uploads/images/a999ceb0110c485e84d74df403e778c2.png)

Set the coordinates for the four anchors, select the serial port for one of them, and click “Start” to begin monitoring.

![上位机结果.png](https://wikiadmin.makerfabs.com/api/uploads/images/5be5feac177b46768b08b04e63543208.png)
