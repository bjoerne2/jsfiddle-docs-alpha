.. _hacks:

================
Hacking jsFiddle
================

.. note::

 Working with CoffeeScript no longer requires to hack jsFiddle. Please visit
 :ref:`panels`

Sometimes jsFiddle does not provide the feature you'd expect. Below is a small 
collection of possible, not harmful hacks.

.. _css_panel_hack:

CSS panel hack
##############
If there is a need to edit the header one can close the ``style`` element and
access the header. After all modifications please open the style tag again

.. code-block:: html
  
 /* your custom CSS \*/
 </style>
 <!-- access to the HEAD element -->
 <style>

Inserting above code in CSS panel will change the CSS section of the header

.. code-block:: html

 <style type='text/css'>
 /* your custom CSS \*/
 </style>
 <!-- access to the HEAD element -->
 <style>
 </style>


.. _paperscript_hack:

Working with PaperScript
########################
In short: Fork http://jsfiddle.net/zalun/xvhFa/ to start a PaperScript fiddle.

Similar to CoffeeScript, PaperScript requires the ``script`` tag to be the 
``type`` of ``text/paperscript`` and provide the ``id`` of the ``canvas`` 
element in the ``canvas`` parameter. Enter following into the HTML panel and 
you'll be able to write PaperScript in JavaScript panel.

.. code-block:: html

 <canvas id="some-unique-id" resize keepalive="true" style='height: 200; width: 200;'></canvas>
 <script>(function(){var s="script",n='\n',d=document,b=d.getElementsByTagName(s)[2].innerHTML.split(n);d.write('<'+s+' type="text/paperscript" canvas="' + document.getElementsByTagName('canvas')[0].id + '">'+b.slice(2,b.length-2).join(n)+'</'+s+'>')})()</script>

Please set the **Code Wrap** to ``no wrap(head)`` (default is ``onLoad``) and
**Franework** to ``No-library (pure JS)``.

As PaperScripts requires this hack to work we can't add it to the list of
frameworks yet. Add a link to 
https://raw.github.com/paperjs/paper.js/master/dist/paper.js
as a **Resource** (:ref:`add_resources`).

Example: http://jsfiddle.net/zalun/LrGEm/12/
