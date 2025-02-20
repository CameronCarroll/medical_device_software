09302408570 SaMD - Software as Medical Device

**Sources:**
1. https://www.fda.gov/medical-devices/digital-health-center-excellence/digital-health-frequently-asked-questions-faqs
2. IMDRF SaMD WG N10/Software as a Medical Device
3. Canary2

**Does FDA regulate SaMD?**
SaMD is defined by IMDRF. For software to be regulated by FDA as a device, the software must meet the definition discussed in [[09272407361 RN FDA Webinar Digital Health]]

**Medical purpose vs non-medical-purpose software**
Software used to make or maintain a device (eg testing, source code management, servicing) is not considered to be software with a medical purpose (by IMDRF).

**Definition of SaMD**
```
Software intended to be used for one or more medical purposes that perform these purposes without being part of a hardware medical device.

NOTES:
- 'without being part of' means software not necessary for a hardware medical device to achieve its intended medical purpose
- Software does not meet the definition of SaMD if its intended purpose is to drive a hardware medical device
- SaMD is a medical device.**Sources:**
1. https://www.fda.gov/medical-devices/digital-health-center-excellence/digital-health-frequently-asked-questions-faqs
2. IMDRF SaMD WG N10/Software as a Medical Device
3. Canary2

**Does FDA regulate SaMD?**
SaMD is defined by IMDRF. For software to be regulated by FDA as a device, the software must meet the definition discussed in [[09272407361 RN FDA Webinar Digital Health]]

**Medical purpose vs non-medical-purpose software**
Software used to make or maintain a device (eg testing, source code management, servicing) is not considered to be software with a medical purpose (by IMDRF).

**Definition of SaMD**
```
Software intended to be used for one or more medical purposes that perform these purposes without being part of a hardware medical device.

NOTES:
- 'without being part of' means software not necessary for a hardware medical device to achieve its intended medical purpose
- Software does not meet the definition of SaMD if its intended purpose is to drive a hardware medical device
- SaMD is a medical device.
```

**Read on functions typical in active implantable ecosystem**
* Software that turns on / off therapy cannot be SaMD *(drives a hardware medical device).*
* Software that programs the therapy parameters cannot be SaMD (*because that software **is** necessary for the hardware implant to meet its intended medical purpose*)
* Software that receives, stores and transmits patient / device information (eg some server collecting device logs / registration information)... *well, depends on whether we are a "Medical Device" per IMDRF definition. I don't think so. I think that's falling on the non-medical-purpose side of things.*
* Software that pushes patches down to the implant (*aka servicing, which was called out as 'not considered software with a medical purpose' in the note in Introduction section of  SaMD WG/N10*)

*Hm, where does that put us for Mainstay? RC/Prog. as SiMD? (software in medical device)? Or software as accessory to medical device...*
```

**Read on functions typical in active implantable ecosystem**
* Software that turns on / off therapy cannot be SaMD *(drives a hardware medical device).*
* Software that programs the therapy parameters cannot be SaMD (*because that software **is** necessary for the hardware implant to meet its intended medical purpose*)
* Software that receives, stores and transmits patient / device information (eg some server collecting device logs / registration information)... *well, depends on whether we are a "Medical Device" per IMDRF definition. I don't think so. I think that's falling on the non-medical-purpose side of things.*
* Software that pushes patches down to the implant (*aka servicing, which was called out as 'not considered software with a medical purpose' in the note in Introduction section of  SaMD WG/N10*)

*Hm, where does that put us for Mainstay? RC/Prog. as SiMD? (software in medical device)? Or software as accessory to medical device...*
