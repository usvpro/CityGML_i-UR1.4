# CityGML-UrbanPlanning-ADE_ver.1.4

Data Encoding Specification of i-Urban Revitalization
CityGML-UrbanPlanning-ADE_ver.1.4

## Introduction
Urban planning has been contributing to the formation of healthy urban environments, preventing disorganized urban sprawl and encouraging infrastructure development in Japan. However, urban areas in Japan, which is facing depopulation and aging society, are at a big turning point. New social issues such as a rapid increase of empty apartments and lands, and non-universal design of facilities lie heavily on their sustainable development, especially regional area. Efficient urban management is required, and municipalities recognize the significance and importance of compact urban development from the perspective of administrative costs.

From this kind of circumstance, the Japanese government strongly promotes i) formation of a high-quality urban revitalization project for regional hub cities, ii) consensus building among those concerned, and iii) investor’s understanding, according to the concepts “Selection and Concentration” and “Respect for Local Intention”.

Recently, the investment climate has changed dramatically with the expansion of the Internet and the development of information communication technologies such as “Fin-Tech”. Information-intensive activities are very important to call for investment.

The “i-UR” is an information infrastructure for urban revitalization. It allows people to analyse and to visualize the situation and problems of urban areas according to the future vision of each area using geospatial information and virtual reality technologies. The quantitative analysis and visualization clearly show the cash-flow and spatial plan of the city and promotes understanding and encourages consensus building among relevant players, e.g. investors, citizens, and developers.

This document defines the encoding specification of the data for i-UR (which is called “i-UR Data”), and aims to assist the formation of social agreement and to improve the quality of urban investment in order to contribute to urban revitalization.
The i-UR Data is the combination of following data:

- a)	3-dimentional city objects and city model
- b)	Detailed information of city objects for analysis
- c)	Constraints/conditions (e.g. regulation) related to urban revitalization
- d)	Statistical grid data for global analysis and visualization 
- e)	Public transit information to consider urban function accumulation in regional planning

<div align="center">
<img width="482" alt="Screenshot 2020-06-22 at 22 24 35" src="https://user-images.githubusercontent.com/67227808/85292663-38ac3680-b4d7-11ea-8b63-6c341d3d27b1.png">
</div>

The i-UR Data Encoding Specification targets on b) to e) data, as a) is already defined in City Geography Markup Language (CityGML). CityGML is an XML/GML based 3D data standard developed by Open Geospatial Consortium (OGC) for the representation, storage and exchange of 3D city models and is widely used in the application fields related to urban areas.

The i-UR Data Encoding Specification is composed of four parts listed below. Each encoding specification is tied up with each component and is an extension of CityGML according to the rules of the Application Domain Extensions (ADE) to ensure data interoperability. Thus i-UR Data aims to be utilized in various application fields, such as disaster prevention, tourism and to carry out urban revitalization.

### Part 1: Urban Object Data Encoding Specification
This document targets on b) Detailed information of city objects for analysis and defines them as properties of CityGML object.
### Part 2: Urban Function Data Encoding Specification	
This document targets on c) Constraints/conditions related to urban revitalization and defines constraints and conditions as subclasses of the root class in CityGML.
### Part 3: Statistical Grid Data Encoding Specification
This document targets on d) Statistical grid data for global analysis and visualization, and defines a statistical grid as subclasses of the root class in CityGML to describe rough city models with a unified unit among cities. 
### Part 4: Public Transit Data Encoding Specification
This document targets on e) Public transit information to consider urban function accumulation in regional planning, and defines a public transit (e.g. bus route, train route) as subclasses of the root class in CityGML.

Figure 2 shows the conceptual structure of the i-UR Data model. The package “UrbanPlanning ADE 1.4” is a collection of four modules which are defined in each part of this encoding specification mentioned above.

<div align="center">
<img width="395" alt="Screenshot 2020-06-22 at 22 27 09" src="https://user-images.githubusercontent.com/67227808/85292890-888afd80-b4d7-11ea-8dc5-f191eafb8cef.png">
</div>

Furthermore, this document defines new Levels of Detail (LOD) for a broad description of city models. These extended LODs enable user to describe rough city models which do not have to be detailed but should be necessary regional or national planning. This ExtendedLOD concept is commonly applied to related modules, and the details of ExtendedLOD is described in Part 2 and Part 3 of this document where this concept is instantiated.

## Concept of Extended LOD
### Introduction
In city planning, it is necessary to harmonize with its higher plans, e.g. the national spatial strategy and the regional plan. These higher plans require rough city models which can be applied on a national or worldwide level for comparison and analysis of cities. For this purpose, this module defines two extended LODs for urban functions. The LOD-1 (minus one) for nationwide city models and the LOD-2 (minus two) for worldwide city models without inconsistency between LOD 0 to 4 as shown in Figure C-1. These extended LODs allow users to employ global 3D city models in policy making phases.

<div align="center">
<img width="435" alt="Screenshot 2020-06-22 at 22 28 27" src="https://user-images.githubusercontent.com/67227808/85293029-bbcd8c80-b4d7-11ea-8229-b67b25e4cdab.png">
</div>

### Extended LODs for Urban Functions
The mechanism of Extended LOD in Urban Function module is implemented as associaions of urf::_UrbanFunction, the root class of this module. To provide an overview of the real world using conceptual and virtual objects, this module defines urf::lod-1MultiGeometry and urf::lod-2MultiGeometry as shown in Figure C-1 to declare explicitly that these objects described in LOD-1 or LOD-2 represent the global city model.

<div align="center">
<img width="297" alt="Screenshot 2020-06-22 at 22 32 20" src="https://user-images.githubusercontent.com/67227808/85293422-46ae8700-b4d8-11ea-9ea6-45dde2c8fd34.png">
</div>

## Samples
There are currently three public data samples for the UrbanPlanning ADE.
- Munakata City https://cesium.com/blog/2020/03/31/i-urban-renovation-visualizes-munakata/
- Chino City(in Japanese) https://www.city.chino.lg.jp/site/kashika/1004.html
- Mutsu City

## More information
OGC CityGML is an open data model and XML-based format for the storage and exchange of semantic 3D city models. It is an application schema for the Geography Markup Language version 3.1.1 (GML3), the extendible international standard for spatial data exchange issued by the Open Geospatial Consortium (OGC) and the ISO TC211. The aim of the development of CityGML is to reach a common definition of the basic entities, attributes, and relations of a 3D city model. By means of so-called Application Domain Extensions (ADEs) the core model of CityGML can be extended systematically by application-specific attributes and object types.

CityGML is an international OGC standard and can be used free of charge.
