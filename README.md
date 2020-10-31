# iShapes Demonstrator Application {ishapes_readme}
[TOC]

# What is it? {#ishapeswhat}
iShapes is an interactive GUI based DDS (Data Distribution Service) Application to learn and test dds key concepts.

It shows and demonstrates the key dds concepts and some of the key DDS Quality of Services (QoSs). It has also been used at the OMG ( Object Management Group) to test the interoperability of the ADLINK DDS products with other compliant DDS implementations.

Each geometrical shape is represented by a dedicated dds topic such as a Circle, Triangle, etc ....

All the geometrical shapes share the same dataType. The dataType structure is modeled in an .idl file.

The shape dataType is characterized by its color, its position in a 2D space and its Size. Shapes with different colors are considered different data objects, i,e different data instances, as the color data attribute is considered the @Key of the dataType. Each data instance has its unique identity, its own lifecycle and its data.


# Building iShapes

The iShapes demo application code is common for Vortex Opensplice and Eclipse Cyclone DDS.  
For Eclipse Cyclone Ishape demo The Cyclone DDS C core, CXX Idl compiler and the C++ binding for Eclipse Cyclone DDS need to be installed before proceeding.   
you can get the Cyclone help from https://github.com/eclipse-cyclonedds/cyclonedds-cxx

For Opensplice Ishape demo Vortex Opensplice DDS need to be installed before proceeding. you can download the Vortex Opensplice DDS from ADLINK Website : https://www.adlinktech.com/en/vortex-opensplice-data-distribution-service

To obtain the ishape demo application, do  

      $ git clone https://github.com/vivekpandey02/Adlink_DDS_Demo_Ishapes    
      $ cd Adlink_DDS_Demo_Ishapes   


## Building Cyclone DDS iShapes

### Building on Linux with cmake
To build the demo you need to have installed a QT5 development environment. 
      
      $ export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:<install-location>
      
       Where <install-location> is the installation directory of your QT5 installation , e.g (/usr/lib/x86_64_linux-gnu/qt5)  

then you should need to simply do the following:

      $ mkdir cyclone_demo_ishapes && cd cyclone_demo_ishapes  
      $ cmake -DADLINK_DDS_PRODUCT=Cyclone -DCYCLONE_INSTALLED_DIR="<install-location>"  
      $ cmake --build . --config Release --target install  
      
      Where <install-location> is the location of Cyclone DDS C++ package  

### Building on Windows with cmake
To build the demo you need to have installed a QT5 development environment. 
The following QT5 environment variables has to be set in order to build and run ishapes:

      C:\> set QTDIR=<QT5-INSTALLATION-DIR> 
      C:\> set QT_PLUGIN_PATH=<QT5-INSTALLATION-DIR>\plugins  
      C:\> set PATH=<QT5-INSTALLATION-DIR>\bin;%PATH%   
      
      Where is the installation directory of your QT5 installation , e.g (<C:\Qt\5.7.1> )  

To build iShape application you should need to simply do the following:

      $ "<install-location>"\release.bat 
      $ mkdir cyclone_demo_ishapes && cd cyclone_demo_ishapes  
      $ cmake -DADLINK_DDS_PRODUCT=Cyclone -DCYCLONE_INSTALLED_DIR="<install-location>"  
      $ cmake --build . --config Debug --target install  
      
      Where <install-location> is the location of the Cyclone DDS C++ package  

## Building Opensplice DDS iShapes

### Building on Linux with cmake

To build the demo you need to have installed a QT5 development environment. Assuming that this is the case, then you should need to simply do the following:

      $ source <install-location>/release.com  
      $ mkdir ospl_demo_ishapes && cd ospl_demo_ishapes  
      $ cmake -DADLINK_DDS_PRODUCT=Ospl  
      $ cmake --build . --config Release --target install  
      
      Where <install-location> is the location of Opensplice DDS Home directory.e. The corresponding Opensplice environment variable is OSPL_HOME. 
  

### Building on Windows with cmake
To build the demo you need to have installed a QT5 development environment.  The following QT5 environment variables has to be set in order to build and run ishapes:

      C:\> set QTDIR=<QT5-INSTALLATION-DIR> 
      C:\> set QT_PLUGIN_PATH=<QT5-INSTALLATION-DIR>\plugins  
      C:\> set PATH=<QT5-INSTALLATION-DIR>\bin;%PATH%  
      C:\> "<install-location>"\release.bat  
      
      Where is the installation directory of your QT5 installation , e.g (<C:\Qt\5.7.1> )  

To build iShape application you should need to simply do the following:

      $ "<install-location>"\release.bat  
      $ mkdir cyclone_demo_ishapes && cd cyclone_demo_ishapes  
      $ cmake .. -DADLINK_DDS_PRODUCT=Cyclone  
      $ cmake --build . --config Release --target install  
      
      Where <install-location> is the location of Opensplice DDS Home directory.  


# Running iShapes

The iShapes demo allows you to publish and subscribe instances of various shapes. The demo is didactic if you run it as at least into two application instances, thus from a shell do one of the below then have one of the applications publish some shapes and press the subscribe button on the other application to receive them.

image-20201022104103958

## Running Cyclone DDS iShapes
### Linux:
cyclone_demo_ishapes is intalled in <install-location>/bin folder of Eclipse Cyclone installation. To run it  you should need to simply do the following:

      $ cyclone_demo_ishapes &  
      $ cyclone_demo_ishapes &  
  
Where <install-location> is the location of Cyclone DDS C++ package  

### Windows:
ospl_demo_ishapes is intalled in <install-location>/bin folder of Eclipse Cyclone installation. To run it  you should need to simply do the following:  
      
      C:\> start cyclone_demo_ishapes  
      C:\> start cyclone_demo_ishapes  
  
Where <install-location> is the location of Cyclone DDS C++ package  

## Running Opensplice DDS iShapes
### Linux:
ospl_demo_ishapes is available in <installation>/bin folder of Opensplice DDS installation directory. To run it  you should need to simply do the following: 

      $ source <install-location>/release.com
      $ ospl_demo_ishapes &
      $ ospl_demo_ishapes &
  
      Where <install-location> is the location of Opensplice DDS Home directory.

### Windows:
      $ "<install-location>"\release.bat 
      C:\> start ospl_demo_ishapes  
      C:\> start ospl_demo_ishapes  
      
      Where <install-location> is the location of Opensplice DDS Home directory.