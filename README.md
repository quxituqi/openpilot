Welcome to openpilot
======

[openpilot](http://github.com/commaai/openpilot) is an open source driving agent.

Currently it performs the functions of Adaptive Cruise Control (ACC) and Lane Keeping Assist System (LKAS) for Hondas and Acuras. It's about on par with Tesla Autopilot at launch, and better than [all other manufacturers](http://www.thedrive.com/tech/5707/the-war-for-autonomous-driving-part-iii-us-vs-germany-vs-japan).

The openpilot codebase has been written to be concise and enable rapid prototyping. We look forward to your contributions - improving real vehicle automation has never been easier.

Hardware
------

Right now openpilot supports the [neo research platform](http://github.com/commaai/neo) for vehicle control. We'd like to support [Open Source Car Control](https://github.com/PolySync/OSCC) as well.

To install it on the NEO:

```bash
# Requires working adb in PATH
cd installation
./install.sh
```

Supported Cars
------

- Acura ILX 2016 with AcuraWatch Plus
  - Limitations: Due to use of the cruise control for gas, it can only be enabled above 25 mph

- Honda Civic 2016 Touring Edition
  - Limitations: Due to limitations in steering firmware, steering is disabled below 18 mph

Directory structure
------

- board         -- Code that runs on the USB interface board
- cereal        -- The messaging spec used for all logs on the phone
- common        -- Library like functionality we've developed here
- dbcs          -- Files showing how to interpret data from cars
- installation  -- Installation on the neo platform
- phonelibs     -- Libraries used on the phone
- selfdrive     -- Code needed to drive the car
  - assets        -- Fonts for ui
  - boardd        -- Daemon to talk to the board
  - calibrationd  -- Camera calibration server
  - common        -- Shared C/C++ code for the daemons
  - controls      -- Python controls (PID loops etc) for the car
  - logcatd       -- Android logcat as a service
  - loggerd       -- Logger and uploader of car data
  - sensord       -- IMU / GPS interface code
  - ui            -- The UI
  - visiond       -- embedded vision pipeline

To understand how the services interact, see `common/services.py`

Adding Car Support
------

It should be relatively easy to add support for the Honda CR-V Touring. The brake message is the same. Steering has a slightly different message with a different message id. Sniff CAN while using LKAS to find it.

The Honda Accord uses different signalling for the steering and probably requires new hardware.

Adding other manufacturers besides Honda/Acura is doable but will be more of an undertaking.


User Data / chffr Account / Crash Reporting
------

By default openpilot creates an account and includes a client for chffr, our dashcam app. We use your data to train better models and improve openpilot for everyone.

It's open source software, so you are free to disable it if you wish. 

It logs the road facing camera, CAN, GPS, IMU, magnetometer, thermal sensors, crashes, and operating system logs.
It does not log the user facing camera or the microphone.

By using it, you agree to [our privacy policy](https://beta.comma.ai/privacy.html). You understand that use of this software or its related services will generate certain types of user data, which may be logged and stored at the sole discretion of comma.ai. By accepting this agreement, you grant an irrevocable, perpetual, worldwide right to comma.ai for the use of this data.

Contributing
------

We welcome both pull requests and issues on
[github](http://github.com/commaai/openpilot). See the TODO file for a list of
good places to start.

Want to get paid to work on openpilot? [comma.ai is hiring](http://comma.ai/hiring.html)

Licensing
------

openpilot is released under the MIT license.

**THIS IS ALPHA QUALITY SOFTWARE FOR RESEARCH PURPOSES ONLY. THIS IS NOT A PRODUCT.
YOU ARE RESPONSIBLE FOR COMPLYING WITH LOCAL LAWS AND REGULATIONS.
NO WARRANTY EXPRESSED OR IMPLIED.**

<h2>The Point Concerning Hair Straightening Brushes</h2>
<p>Hair straightening brushes can be better and faster than straightening with a hair dryer or perhaps a flat iron. A hair straightening brush keeps your hair from appearing flat when straightening as well. Since the bristles partition your hair from the heating plate, hair straightening brushes are less likely to harm your hair. Compared to hair straightening brushes, flat irons break up hydrogen bonds that can be quite ruining for your hair. Hair straightening brushes are actually anti-static, that may help you to keep your hair frizz free. </p>
<h2>The Group Regarding the Authentic Straightening Brush</h2>
<p>Hair straightening brushes received their beginning with DAFNI, coming from Italy. Doing in the basement, Kobi and Sharon Rani made and crafted the <a href="http://besthairstraighteningbrushes.com/">best hair straightening brush</a>. Using their mutual history in engineering, father plus daughter created a hair straightening product. DAFNI had been branded after Sharon's younger sister, and this stands for "laurel" in Greek. </p>
<h2>The Essentials regarding Hair Straightening Brushes</h2>
<p>Combining two different instruments, the hair straightening brush will make hair styling the hair effortless and instant. When you are somebody who prefer to sport sleek as well as straight hairstyles, you might like to look into this. The hair straightening brush is usually an electric powered tool just like a hair iron, that you simply should connect to employ. You can see a hair straightening brush as a flat iron together with bristles. </p>
<h2>Hair Straightening Brushes: A How-To Instruction</h2>
<p>I'm sure you are delighted, but it is recommended if you guard your hair primarily before going at it by using a hair straightening brush. Remedies that have keratin and protein may actually help condition and boost the hair. You need to comb or simply brush your hair before you apply heat with a straightening brush. Ensure that the locks are dry or perhaps probably dry prior to applying this item in order to prevent harm. It is all about avoiding problems, not responding into it -- it is certainly hard to repair the hair as soon as it's harmed. </p>
<h2>Distinctive Functions of the Hair Straightening Brush</h2>
<p>Straighten and also nurture your hair together with straightening brushes that has boar hair bristles. Heat management on straightening brushes may help you avoid harming your hair unnecessarily. If you'd like another handy straightening brush, look into the forms which can be battery powered compared to wall socket operated. </p>

