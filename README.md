# The Anatomy of AMF (Additive Manufacturing File Format)

## What is AMF?

> Additive manufacturing file format (AMF) is an open standard for describing objects for additive manufacturing processes such as 3D printing.
> ([Wikipedia](https://en.wikipedia.org/wiki/Additive_manufacturing_file_format))

## AMF Structre

AMF is basically an XML file and contains several different sections to define 3D object(s).

At maximum use AMF can have the following structre, however some of these tags are rarely used;


As with all XML files it (optionally) starts with the XML version and encoding definition.

```xml
<?xml version="1.0" encoding="utf-8"?>
```

Also every AMF file should be enclosed within `<amf> ... </amf>` tags. An amf tag starts with the unit definition, and version number;

```xml
<amf unit="mm" version="1.0">
  ...
</amf>
```
Traditionally AMF files starts with `<metadata>` definitions. That may be authors name, date it was created or any information about the objects contained in the file.

```xml
<metadata type="name_of_the_file">An Object</metadata>
<metadata type="dateCreated">12.17.2020</metadata> 
```

So far we've defined a plain simple file that we can call an AMF file;

```xml
<?xml version="1.0" encoding="utf-8"?>
<amf unit="mm" version="1.0">
  <metadata type="name_of_the_file">An Object</metadata>
  <metadata type="dateCreated">12.17.2020</metadata> 
  ...
</amf>
```
At this point forward everything is ready for us to define the 3D shape, which is called `object` in the AMF standard.

### Objects in AMF
The geometry, and volume definitions for an object is defined within `<object>` tags. This tag requires following tags;

* Mesh `<mesh>`
  * Vertices `<vertices>`
  * Volume `<volume>`
  
 In contrast to other formats, AMF divides vertices and volume definitions, this brings more clarity and flexibility to the standard.
 
 ### References
 * AMF Tutorial: The Basics (Hod Lipson)
