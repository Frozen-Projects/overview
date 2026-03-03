# UE5 OpenCASCADE Wrapper (CAD Importer)
Factories are always changing and improving for various reasons such as increasing observability or replacing hard-to-find parts with alternatives at maintenance operations. Most of the time, these changes include company-specific know-hows. So, companies don't want to share their 3D models after some level. 
For this reason, runtime import solutions are the most important feature of 3D digital twin training simulation editors. 
In order to solve that, I am working on OpenCASCADE wrapper for Unreal Engine 5. 

## Currently it has these features. 
- STEP and IGES to GLB converter 
- STEP and IGES hierarchy exporter as JSON 

The converted GLB model contains all names and hierarchy correctly. So, we can import them at runtime with all platforms. 
Besides this, I am working on fully functional CAD importer feature. Right now it can export vertex locations and I can create static meshes with them by using geometry scripts, Static Mesh LOD Resources and Static Mesh Descriptions. But I need to improve normals, UV and tangent calculations. 
The library itself can support native CAD formats such as IAM, SLDASM and Parasolid but these extensions require paid subscription. So, they disabled but I can easily enable them. 

## VIDEOS 
https://www.linkedin.com/feed/update/urn:li:activity:7294055483185795073/

# UE5 Mesh Operations
My open source plugin has these runtime features. 
Change pivot location of static, 
Generate static mesh (not dynamic or procedural mesh. actual static mesh), 
Create static, procedural and scene components with user defined names, 
Some helpers for automatic shapes 
The plugin simplifies the creation of runtime importers. Because it handles all render data of Unreal Engine. 

## GitHub Link 
https://github.com/Frozen-Projects/MeshOperations

# Runtime Certificate Generators (MBedTLS & OpenSSL)
- Self signed certificate creation
- Helper Templates (OPC UA v1.4)
- User can add ``Subject Alternative Names`` to MbedTLS

# UE5 OPC UA Client 
I developed open62541 based OPC UA client plugin for Unreal Engine 5 to access industrial machine data in real time. 

## Current Features
- Both anonymous and secure connections, 
- Self signed certificate creation with help of my ``Runtime Certificate Generators Plugins``.
- Asynchronous historical access (if server supports it) 
- Node browser, 
- Reader & Writer
- FRunnableThread based bulk reader to read high volumed data without main thread performance decrease
- PubSub (UDP)
- Fully blueprint exposed

## Supported Platforms
- Windows
- Android

## Usecases
- 3D HMI
- Remote Manufacturing
- Predictive maintenance related digital twins
- OT to IT Bridges such as OPC UA to HTTP, MQTT and Databases

## VIDEOS 
- OPC UA to REST API : https://www.linkedin.com/posts/eryozr_ue-ue5-unreal-activity-7134909446283046913-Hyp0/
- Simple Factory Dashboard  : https://drive.google.com/file/d/1CIrD6rjYalW8-rYgldH6h7bdymMwFNPN/view?usp=drive_link
- Android Client Sample : https://www.linkedin.com/feed/update/urn:li:activity:7017586141168082944/
- MBedTLS Certificate Generator : https://www.linkedin.com/feed/update/urn:li:activity:7292000353326174208/

