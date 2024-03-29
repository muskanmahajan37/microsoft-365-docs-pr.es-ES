---
title: Cómo se identifica el contenido para las recomendaciones de gobierno de datos
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: El Centro de seguridad y cumplimiento de Microsoft 365 ofrece recomendaciones para el gobierno de datos según la configuración actual de su organización y le permite realizar configuraciones con un par de clics. Algunas de estas recomendaciones detectan el contenido específico de su organización y, luego, proporcionan pasos recomendados para administrarlo. Por ejemplo, una recomendación puede detectar los elementos que contienen contenido crítico para la empresa (como privilegios abogado-cliente o información NDA) y hacer que pueda aplicar automáticamente una etiqueta de retención a dichos elementos para asegurarse de que están clasificados y se conservan según sea necesario. En este tema se enumeran las recomendaciones de gobierno de datos que puede ver y se describe el contenido que se detecta para desencadenar cada uno.
ms.openlocfilehash: 9a022369fb783a498971c91664fa6532472d8589
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922614"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a>Cómo se identifica el contenido para las recomendaciones de gobierno de datos

El Centro de seguridad y cumplimiento de Office 365 ofrece recomendaciones para el gobierno de datos según la configuración actual de su organización y le permite realizar configuraciones con un par de clics. Algunas de estas recomendaciones detectan el contenido específico de su organización y, luego, proporcionan pasos recomendados para administrarlo. Por ejemplo, una recomendación puede detectar los elementos que contienen contenido crítico para la empresa (como privilegios abogado-cliente o información NDA) y hacer que pueda aplicar automáticamente una etiqueta de retención a dichos elementos para asegurarse de que están clasificados y se conservan según sea necesario. 

En este tema se enumeran las recomendaciones de gobierno de datos que es posible que vea y se describe el contenido que se detecte para desencadenar cada uno.

## <a name="clean-up-voicemail"></a>Limpiar el correo de voz

Esta recomendación aparece cuando se detectan mensajes de correo identificados como tipo de mensaje "correo de voz" en los buzones de usuarios. Obtenga más información sobre las [propiedades de mensajes en Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).

## <a name="label-attorney-client-privilege-content"></a>Etiquetar contenido de privilegios abogado-cliente  

Esta recomendación aparece cuando se cumple uno de los siguientes criterios.

- Cualquier combinación de estas palabras clave se detecta en el cuerpo de un mensaje de correo electrónico:
    - ACP
    - Privilegio de abogado cliente
    - Privilegio de abogado-cliente
    - Confidencialidad abogado-cliente

- Cualquier combinación de estas palabras clave se detectan en archivos de SharePoint o OneDrive:
    - ACP
    - Privilegio de abogado cliente*
    - Privilegio AC

## <a name="retain-audio-files"></a>Conservar archivos de audio

Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.

- .MP3
- .WMA
- .WAV
- .RA
- .RAM
- .RM
- .MID
- .OGG
- .AIFF
- .PCM
- .AAC
- .FLAC
- .ALAC

## <a name="retain-cad-files"></a>Conservar archivos CAD

Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.

- .3DXML
- .ACIS
- .ARC
- .ASM
- .CAT*
- .CGR
- .DW*
- .DX*
- .EDRW
- .IAM
- .IGES
- .IGS
- .IPT
- .JT
- .MF1
- .NEU
- .PAR
- .PKG
- .PRC
- .PRT
- .PSM
- .PWD
- .SLD*
- .STEP
- .STL
- .STP
- .U3D
- .UNV
- .VRML
- .WRL
- .X_*
- .XAS
- .XMT*
- .XPR

## <a name="retain-image-files"></a>Conservar archivos de imagen

Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.

- .JPEG
- .GIF
- .TIF*
- .BMP
- .PNG
- .RAW
- .PSD
- .PSP
- .JPG
- .EXIF
- .PPM
- .PGM
- .PBM
- .PNM
- .WEBP

## <a name="retain-nda-content"></a>Conservar contenido NDA 

Esta recomendación aparece cuando se cumple uno de los siguientes criterios.

- Cualquier combinación de estas palabras clave se detecta en el cuerpo de un mensaje de correo electrónico:
    - NDA
    - “Acuerdo de confidencialidad”
    - “Acuerdo de confidencialidad”

- Cualquier combinación de estas palabras clave se detectan en archivos .PDF o .DOC en SharePoint o OneDrive:
    - NDA
    - Acuerdo de confidencialidad

## <a name="retain-software-development-files"></a>Conservar archivos de desarrollo de software 

Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.

- .ASAX
- .ASM
- .ASP*
- .BAT
- .CONFIG
- .CS
- .CSS
- .DISCO
- .HTM*
- .INC
- .JAD
- .JAVA
- .JS*
- .LIB
- .O
- .PHP
- .RC
- .RESX
- .RPT
- .RSS
- .SCPT
- .SRC
- .VB*
- .WSF
- .XCODEPROJ
- .XML
- .XSD
- .XSL*

## <a name="retain-video-files"></a>Conservar archivos de vídeo

Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.

- .AVCHD
- .AVI
- .FLV
- .MOV
- .MP2V
- .MP4
- .MP4V
- .MPE
- MPEG
- .MPEG1
- .MPEG2
- .MPEG4
- .MPG
- .MPG2
- .MPG4
- .WMV
- .XMV