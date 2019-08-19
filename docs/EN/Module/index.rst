Component Overview 
==============================================
AAPS is not just a (self-built) application, the application is a just one of serveral modules. Before deciding for one, it would be a good idea to have a look at the Hardware Setup, too.

Here should be a nice overview (image).

Necessary Modules
=====================
Phones
-------
Users are creating a `list of tested phones and watches <https://docs.google.com/spreadsheets/d/1gZAsN6f0gv6tkgy9EBsYl0BQNhna0RDqA9QGycAqCQc/edit?usp=sharing>`_

You can use filters to display particular pumps or phones but please set back to view all when you've finished looking, ready for the next person to view all.

To record a phone or watch that isn't already listed in the spreadsheet then please fill in the `form <https://docs.google.com/forms/d/e/1FAIpQLScvmuqLTZ7MizuFBoTyVCZXuDb__jnQawEvMYtnnT9RGY6QUw/viewform>`_

Any problems with the spreadsheet please email `hardware@androidaps.org <mailto:hardware@androidaps.org>`_, any donations of phone/watch models that still need testing please email `donations@androidaps.org <mailto:hardware@androidaps.org>`_.

Insulin Pump
------------
Please update this section for medtronic and insight pump.

AndroidAPS currently works with 

- Accu-Chek Combo (additional needed: Ruffy, LineageOS or Android 8.1 on your phone)
- Accu-Chek Insight
- DanaR
- DanaRS  

pumps. Details of the status of other pumps that may have the potential to work with AndroidAPS are listed on the `Future (possible) Pumps <Future-possible-Pump-Drivers.html>`_ page.

If you need to choose a pump to upgrade to or buy then people often ask which to choose. Details of the various distributors is in `this spreadsheet <https://drive.google.com/open?id=1CRfmmjA-0h_9nkRViP3J9FyflT9eu-a8HeMrhrKzKz0>`_, please share the details of yours if not already listed.

The Combo and the Insight are solid pumps, and loopable. The advantages of the DanaR/RS as the pump of choice however are:

* The Dana*R/RS connects to almost any phone with Android >= 5.1 without the need to flash lineage. If your phone breaks you usually can find easily any phone that works with the Dana*R/RS pumps as quick replacement... not so easy with the Combo. (This might change in the future when Android 8.1 gets more popular)

* Initial pairing is simpler with the Dana* RS. But you usually only do this once so it only impacts if you want to test a new feature with different pumps.

* So far the Combo works with screen parsing. In general that works great but it is slow. For looping this does not matter much as everything works in the background. Still there is much more time you need to be connected so more time where the BT connection might break, which isn't so easy if you walk away from your phone whilst bolusing & cooking. 

* The Combo vibrates on the end of TBRs, the Dana* R vibrates (or beeps) on SMB. At night time you are likely to be using TBRs more than SMB.  The Dana* RS is configurable that it does neither beeps or vibrates.

* Reading the history on the RS in a few seconds with carbs makes it possible to switch phones easily while offline and continue looping as soon a soon as some CGM values are in.

* All pumps AndroidAPS can talk with are waterproof on delivery. Only the Dana pumps are also "waterproof by warranty" due to the sealed battery compartment and reservoir filling system. 

The Combo of course is a very good pump, and loopable. It also has the advantage of many more infusion set types to choose from as it has a standard luer lock. And the battery is a default one you can buy at any gas station, 24 hour convenience store and if you really need one, you can steal/borrow it from the remote control in the hotel room ;-)


BG Source
------------
This is just a short overview of all compatible CGMs/FGM with AndroidAPS. For further details, look `here <../Configuration/BG-Source.html>`_. Just a short hint: if you an display your gluose data in xDrip+ or Nightscout, you can have xDrip+ has BG Source in AAPS.

* Dexcom G4: These sensors are quite old, but you can find instructions on how to use it with xDrip+
* Dexcom G5: It works with xDrip+ or patched Dexcom App
* Dexcom G6: It works with xDrip+ or patched Dexcom App
* Libre 1: You need a transmitter for it (built or buy it yourself) and xDrip+
* Libre 2: There are instructions in the Internet on how to use it with xDrip+ (and no transmitter)
* Eversense: It works so far only together with ESEL and a patched Eversense-App (works not with (and only with all three components): Dana RS, LineageOS)
* Enlite: quite complicated with a lot of extra stuff


Nightscout
------------
One senctence: what is `Nightscout <http://www.nightscout.info/>`_
Nightscout is independent of the other modules.
More information on how to configure Nightscout for use with AndroidAPS `here <../Installing-AndroidAPS/Nightscout.html>`_

AAPS-.apk file
------
The basic component of the system. Before installing the app, you have to build the apk- file (the "app-file" first). Instructions are  `here <../../Installing-AndroidAPS/Building-APK.html>`_. 
   
   
 

Optional Modules
==================
Smartwatch
---------------
Users are creating a [list of tested phones and watches](https://docs.google.com/spreadsheets/d/1gZAsN6f0gv6tkgy9EBsYl0BQNhna0RDqA9QGycAqCQc/edit?usp=sharing). There are different watchfaces for use with AAPS, which you can find `here <../Configuration/Watchfaces>`_.

 
Sample Setup
============
You can find a Sample Setup here: `Sample Setup: Samsung S7, Dana-R, Dexcom G5 and Sony Smartwatch <../Getting-Started/Sample-Setup.html>`_.

.. toctree::
   :maxdepth: 1
   :glob:
   
   `Sample Setup <../Getting-Started/Sample-Setup.md>
  

It sometimes takes a while until all module are together. But no worries, there are a lot of things you can do while waiting. It is NECESSARY to check and where approporiate adapt basal rates (BR), insulin-carbration (IC), insulin-sensitivity-factores (ISF), etc. And if already possible, open loop is a good way to test the system.

If you have your AAPS components all together (congrats!) or at least enough to start with an open loop, you should first read through the `Objectiv description <../Usage/Objectives.html>`_ (Overview Part 2 )before each new Objectiv.


