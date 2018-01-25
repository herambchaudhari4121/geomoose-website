GeoMoose 2 Coding Standards
===========================


1. Code Formatting.  

 a. Tabs, not spaces.  This formatting rule is a a matter of religion.  GeoMoose worships in the House of "\\t".  Code submissions will be returned if the indentation uses spaces.

 b. function brackets should be at the end of a function declaration. 

  **Bad**::

     foo: function ()
     {
     }

     function foo ()
     {
     }

  **Good**::

     foo: function () {
     }

     function foo() {
     }

 c. Methods should be camelCased.
 d. Private methods should begin with an underscore. ::

     _myPrivateMethod: function () {
     }

 e. Variable names inside of methods and functions should use under case and be underscore delimited. ::

     var my_variable_in_a_function = 0;

 f. Please format comments to be parsed with NaturalDocs.  This is the same library used by OpenLayers.  This allows for better class and API documentation building.

2. Do not create new dependencies in the core.  Adding a library dependency is not something the GeoMoose team takes lightly.  By comparison to other Web GIS distributions we strive to keep GeoMoose very light.  We work quite hard to keep it appropriate for distribution to the public and to devices with limited bandwidth.

3. DRY - Don't Repeat Yourself.  

 a. Scour the documentation first, especially the GeoMoose API namespace, there is a lot of functionality there.

 b.  Check OpenLayers, especially OpenLayers.Util.

 c. Subclass! Copying and pasting is ugly and creates long term support-ability issues.  You are very likely copying and pasting the bugs into your code.

4. Keep UI and Library code separate.  It may be tempting, with Javascript, but please keep oil out of the water - fragile sea-life depends on you.  In a more serious note, if a function is meant to put content somewhere, write a function that generates the content in a machine parse-able format and separate code that renders it.

5. All diff/patch files should indicate a version. Patches can be sent to the GeoMoose mailing list.  The email should include a major GeoMoose version or an SVN revision number.

6. All code submitted to GeoMoose should be free and clear of all license restrictions.  If any one can claim ownership, a license, patent, or copyright we will reject the code.  If you are not on the committers list then please include a message releasing the code into the public domain.  Please reference the GeoMoose license for the terms under which GeoMoose is distributed.

7. Any contributed code should contain a code source comment block in each file header indicating the author (that is you and your employer if you are working on company time), date of contribution and any conflicting licensing restrictions that are not already covered by the GeoMoose :ref:`license`. All unusual situations need to be discussed and/or documented on the project mail list and/or in the project TRAC system. 

Here are some example comment blocks for code contributors:

If you donated a file to the GeoMoose project, using an MIT license, the comment block would include:

     Copyright (c) 2013, <YourName> (<YourCompanyName>)
     
     Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
     
     The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
     
     THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

The accepted project code would be distributed as:

     Copyright (c) 2013 Dan "Ducky" Little & Geomoose.org
     
     Copyright (c) 2013, <YourName> (<YourCompanyName>)
     
     Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sub-license, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
     
     The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
     
     THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
