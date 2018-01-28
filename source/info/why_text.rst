.. include:: /info/why_abstract.rst

The GeoMoose demo shows rendering parcels in the popular Spherical Mercator projection.  These parcels are coming from a Shapefile which is stored in UTM-15N.  It also demonstrates how to re-project a local WMS service from native coordinates into Spherical Mercator.  This allows users to compare local data seamlessly with popular web mapping services such as Google, Bing, and MapQuest.  These are some of the most common tasks performed with MapServer and GeoMoose includes real, working, and practical examples.

Beyond rendering, gaining information on a dataset is an important every day use of a Web GIS.  GeoMoose includes all of the basic tools for traditional selection, identification, and searching on a dataset.  However, GeoMoose's functionality is not limited by those services.  To power that functionality we have developed a power service-based architecture that users can use to create their own custom scripts in any language.

As of the 2.6 version, GeoMoose includes new powerful vector capabilities.  While not seen in the default demo, GeoMoose can work with a WFS-T server to create, edit, and delete features in a dataset.  The styling is defined in the GeoMoose mapbook and the layers can even be printed to a PDF!

Finally, GeoMoose is designed with lightweight-extensibility in mind.  There are a myriad of custom configuration options, a highly flexible services architecture, and a powerful user-extension model.  GeoMoose can create powerful web GIS applications for those with no programming knowledge and provides an astounding platform for those willing to write some code.

