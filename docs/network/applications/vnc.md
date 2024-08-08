# VNC
```
      +---------------+                              +---------------+
      |               |                              |               |
      |  VNC Client   | <----RFB Protocol over---->  |  VNC Server   |
      | (Viewer)      |          TCP/IP             |               |
      |               |                              |               |
      +---------------+                              +---------------+
             ^                                             ^
             | User Input                            Framebuffer Updates
             v                                             v
      +----------------+                         +-------------------+
      |  User's Device |                         | Remote Device     |
      |  (Laptop, PC)  |                         | (Server, PC, etc.)|
      +----------------+                         +-------------------+
```
