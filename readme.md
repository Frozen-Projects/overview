# Project Overviews
You can read our important (including private ones) plugins' details and their motives in here.

# No-Code Maintenance Training Editor
I developed a no-code editor to allow factory maintenance supervisors to create their maintenance training simulations without coding or scripting knowledge. 

### Workflow 
1. Import 3D Models 
2. Describe scenario by writing 
3. Make necessary movement for once 

(Video can be shared privately)

# LLAMA.CPP Plugin
This plugin allows digital twins to harvest power of LLMs at local.

### Roadmap
- Conversation history
- Import and export chat history
- RAG implementation
- Visual Processing

# UE5 OpenCASCADE Wrapper (CAD Importer)
Factories are always changing and improving for various reasons such as increasing observability or replacing hard-to-find parts with alternatives at maintenance operations. Most of the time, these changes include company-specific know-hows. So, companies don't want to share their 3D models after some level. 
For this reason, runtime import solutions are the most important feature of 3D digital twin training simulation editors. 
In order to solve that, I am working on OpenCASCADE wrapper for Unreal Engine 5. 

### Currently it has these features. 
- STEP and IGES to GLB converter 
- STEP and IGES hierarchy exporter as JSON 

The converted GLB model contains all names and hierarchy correctly. So, we can import them at runtime with all platforms. 
Besides this, I am working on fully functional CAD importer feature. Right now it can export vertex locations and I can create static meshes with them by using geometry scripts, Static Mesh LOD Resources and Static Mesh Descriptions. But I need to improve normals, UV and tangent calculations. 
The library itself can support native CAD formats such as IAM, SLDASM and Parasolid but these extensions require paid subscription. So, they disabled but I can easily enable them. 

### VIDEOS 
https://www.linkedin.com/feed/update/urn:li:activity:7294055483185795073/

# UE5 Mesh Operations
My open source plugin has these runtime features. 
Change pivot location of static, 
Generate static mesh (not dynamic or procedural mesh. actual static mesh), 
Create static, procedural and scene components with user defined names, 
Some helpers for automatic shapes 
The plugin simplifies the creation of runtime importers. Because it handles all render data of Unreal Engine. 

### GitHub Link 
https://github.com/Frozen-Projects/MeshOperations

# Runtime Certificate Generators (MBedTLS & OpenSSL)
- Self signed certificate creation
- Helper Templates (OPC UA v1.4)
- User can add ``Subject Alternative Names`` to MbedTLS

# UE5 OPC UA Client 
I developed open62541 based OPC UA client plugin for Unreal Engine 5 to access industrial machine data in real time. 

### Current Features
- Both anonymous and secure connections, 
- Self signed certificate creation with help of my ``Runtime Certificate Generators Plugins``.
- Asynchronous historical access (if server supports it) 
- Node browser, 
- Reader & Writer
- ``FRunnableThread`` based bulk reader to read high volumed data without main thread performance decrease
- PubSub (UDP)
- Fully blueprint exposed

### Supported Platforms
- Windows
- Android

### Usecases
- 3D HMI
- Remote Manufacturing
- Predictive maintenance related digital twins
- OT to IT Bridges such as OPC UA to HTTP, MQTT and Databases like **ProSYS DataForge** and **PTC Kepware DataLogger**.

### VIDEOS 
- OPC UA to REST API : https://www.linkedin.com/posts/eryozr_ue-ue5-unreal-activity-7134909446283046913-Hyp0/
- Simple Factory Dashboard  : https://drive.google.com/file/d/1CIrD6rjYalW8-rYgldH6h7bdymMwFNPN/view?usp=drive_link
- Android Client Sample : https://www.linkedin.com/feed/update/urn:li:activity:7017586141168082944/
- MBedTLS Certificate Generator : https://www.linkedin.com/feed/update/urn:li:activity:7292000353326174208/

# UE5 Modbus Client
I developed libmodbus based modbus client plugin for Unreal Engine 5 to access legacy industrial machine data in real time.

### Videos
https://www.linkedin.com/feed/update/urn:li:activity:7226946032792698880/

# General Database Connector
I integrated ``Microsoft ODBC``, ``OLEDB``, ``mongocxx``, ``libpqxx``, ``sqlite`` libraries to access various databases from Unreal Engine 5 at runtime.

### Mongocxx Specific Features
- All crud operations (insert, update, delete, replace and their find... variants)
- Get all or specific data
- Aggregation System
- Monitoring System
- Transactions

### Others
- To solve ``forward cursor only`` problem of SQL clients, I hold data at cache. So, users can process specific sections of data at different times without re-execution.

# MQTT Clients
Eclipse Paho C based MQTT client libraries.
- Sync: https://github.com/Frozen-Projects/FF_MQTT_Sync
- Async: https://github.com/Frozen-Projects/FF_MQTT_Async

## LibHV Based HTTP Server Library
Digital twins projects are not just fancy visualizing tools for industrial data. Sometimes we may want to feed other MES (manufacturing execution systems) products with our processed data. In these cases, HTTP servers can help us. Current HTTP server solutions of UE5 are blocking types or use main thread. So, they can't satisfy performance requirements when there are too much API requests. To solve that, I integrated ``LibHv`` library to UE5.

### Github
https://github.com/Frozen-Projects/FF_HTTP_LHV

# UE5 License Spring Wrapper
Software licenses are fundamental for anti-piracy. License Spring offers easy-to-use cloud based licensing solutions. So, I created a blueprint exposed plugin that can talk with their servers.

## Why did I develop That ?
They claim that they have UE5 plugin but they don't They only have ``binary C++ SDK`` with a specific ``OpenSSL`` version and it is a big problem. Because UE5 already has a version of OpenSSL (1.1t) and Epic used it in too much modules, we can't directly update or integrate a different version.</br>
I know that, we can use only DLL files of different OpenSSL versions if all ``OpenSSL`` includes are in ``.cpp`` files and argument signatures use opque pointers like ``void*``. However, we can use this method for only a single different version and I would like to use ``OpenSSL 3``. But because License Spring doesn't give us actual source code, we can't change its OpenSSL version and they don't have any blueprint interface.</br>
To solve all these issues, I reverse engineered their JavaScript code to write Unreal Engine optimize wrapper from scratch. It can check (including customer informations), activate and deactivate current license at runtime. 

# UE5 PDFium Wrapper
PDFium wrapper to create and edit PDF files at runtime.

### Platform Support
- Windows
- Android

### Features
- Add images to PDF 
- Add external fonts to PDF 
- Render PDF file 
- Extract images, texts, web links, fonts with their position information and import them to UE5 
- Select text in PDF 

### GitHub Link 
https://github.com/Frozen-Projects/FF_PDFium

# Screen and Window Recorder Plugin
I developed ``Microsoft Win32 BitBlt API`` based screen and window recorder plugin. It can send keyboard and mouse commands to the PC. So, you can bring **Horizon Workspace** or **Apple Vision Pro** screen streaming features to UE5.

### Use Cases
- Control CAD application like Autodesk Inventor or Solidworks from UE5 and bring 3D model to the simulation.

### Why BitBlt ?
Notebooks with multiple GPUs (for example AMD APUs or Intel Iris / HD Graphics), can cause problems with other technologies. Because while Unreal Engine 5 uses high-end GPUs, other windows such as Google Chrome or Microsoft PowerPoint use internal GPU. So, UE5 can't capture these windows. To solve performance problem, I used ``FRunnableThread``.

### Github Link 
https://github.com/Frozen-Projects/WinInputs

# Window Manager
### Features
- External window creation at runtime
- File and folder drag drop support at runtime 
- File explorer dialogs (save, open files and directories) 
- Custom viewport client to create multi-view projects such as **Autodesk 3Ds Max**
- Changing layout of local multiplayer 
- Changing layout's background 

### GitHub Link 
https://github.com/Frozen-Projects/WindowSystem

### Custom Viewport Usage Sample 
https://www.linkedin.com/feed/update/urn:li:activity:7274327445254602753

# Runtime Logger
It catches all ``UE_LOG`` based logs and exposes it to blueprint interface for more advance processing and visualization.
