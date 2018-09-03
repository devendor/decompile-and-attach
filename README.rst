Decompile and Attach
====================

A plugin for IntelliJ java ides to allow bulk decompile of jars decompiler embedded in their IDEs.

:Original Author: `Babur`_:
:Forked from: `babur/decompile-and-attach`_:
:Maintained by: `rferguson`_:
:Version: 1.8:

Details
-------

A rework of the original decompile and attach plugin for IntelliJ IDEA provided by
`Babur`_ for compatibility with current versions of IntelliJ idea.

Decompile and attach decompiles jar packages using Intellij's Fernflower decompiler
and attaches decompiled source jars to your project within intellij java ides.

The decompiled source is included within Search Scopes or can be unpacked and analyzed however you wish.

Select one or more jar files in the project menu. Then right click and select the "Decompile And Attach" action.

Check your event log for warnings. Failure to decompile will log a warning and continue to the next jar.

Don't expect perfection. It's a good decompiler, but can't reproduce original source code.

Changlog
--------

.. raw:: html

   <!--pasted from build.gradle -->
   <b>1.8 rferguson 09/03/2018</b>
   <br/><ul>
   <li>Moved plugin to com.devendortech namespace.</li>
   <li>Updated for compatibility with IU-182.4129.33</li>
   <li>Add try / catch so decompile logs warning and continues when something doesn't decompile.</li>
   <li>Transitioned to gradle plugin dev framework.</li>
   <li>Releasing to IntelliJ as the original author has abandoned his project.</li>
   </ul>
   <b>1.7 rferguson 11/9/2017</b>
   <br/><ul>
   <li>Fix for idea 172 builds</li>
   <li>plugin.xml in 1.6 excludes support for 2017.2 releases.
   1.5 allows it but doesn't work change to plugin.xml to allow this
   to install on newer release</li>
   <li>The file list included the jar name itself which was passing through
   to attach and causing an fault</li>
   <li>An empty directory would pass through to decompile and cause a fault.</li>
   <li>Any non-class files were excluded from source export jars which
   limited context like reflections and packages.</li>
   <li>The above covers issues 9, 10, 12 and 13 from <a href="https://github.com/bduisenov/decompile-and-attach/issues">Babur's github repo</a></li>
   </ul>
   <b>1.6 babur 12/03/2016</b><br/>
   fixed plugin for Intellij 163
   <br/>
   <b>1.5 babur 12/1/2015</b>
   <br/>
   <ul>
   <li>jar decompilation continues even if decompilation for some classes failed</li>
   <li>added multiple jars decompilation</li>
   <li>added cancellation for process</li>
   <li>added form for selecting folder where sources would be stored</li>
   <li>switched from BYTECODE_SOURCE_MAPPING to USE_DEBUG_LINE_NUMBERS for decompiler. fix see github issue #6</li>
   </ul>
   <br/>
   <b>1.4 babur 11/27/2015</b><br/>
   decompiled sources are attached to source jar lib instead of creating a new lib
   <br/>
   <b>1.3 11/23/2015 babur</b><br/>
   added functionality for attaching decompiled sources to owner module of a jar
   <br/>
   <b>1.2 11/18/2015 babur</b><br/>
   fixed jar archive generation.
   <br/>
   <b>1.1 11/17.2015</b><br/>
   fixes
   <ul>


.. _Babur: https://github.com/bduisenov
.. _babur/decompile-and-attach: https://github.com/bduisenov/decompile-and-attach
.. _rferguson: https://github.com/devendor
