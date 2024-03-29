---
title: Cifrado de datos en OneDrive para la Empresa y SharePoint Online
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Entienda los elementos básicos del cifrado de seguridad de datos en OneDrive para la Empresa y SharePoint Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca93d04fa21487ad054cd9cb924dff1fc15abfbd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922634"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>Cifrado de datos en OneDrive para la Empresa y SharePoint Online

Entienda los elementos básicos del cifrado de seguridad de datos en OneDrive para la Empresa y SharePoint Online.
  
## <a name="security-and-data-encryption-in-office-365"></a>Seguridad y cifrado de datos en Office 365

Microsoft 365 es un entorno altamente seguro que ofrece una protección extensa en varias capas: seguridad del centro de datos físico, seguridad de red, seguridad de acceso, seguridad de aplicaciones y seguridad de datos. Este artículo se centra específicamente en el lado del cifrado en tránsito y en reposo de la seguridad de datos para OneDrive para la Empresa y SharePoint Online.
  
Vea cómo funciona el cifrado de datos en el siguiente vídeo.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>Cifrado de datos en tránsito

En OneDrive para la Empresa y SharePoint Online, hay dos escenarios en los que los datos entran y salen de los centros de datos.
  
- **Comunicación del cliente con el servidor** La comunicación con OneDrive para la Empresa a través de Internet usa conexiones SSL/TLS. Todas las conexiones SSL se establecen con claves de 2048 bits.

- **Movimiento de datos entre centros de datos** La razón principal para mover datos entre centros de datos es que la replicación geográfica habilite la recuperación ante desastres. Por ejemplo, los registros de transacciones y diferencias de almacenamiento de blobs de SQL Server recorren esta canalización. Mientras que estos datos ya se transmiten mediante una red privada, tendrán una mayor protección con el mejor cifrado de su clase. 

## <a name="encryption-of-data-at-rest"></a>Cifrado de datos en reposo

El cifrado en reposo incluye dos componentes: cifrado de nivel de disco de BitLocker y cifrado por archivo del contenido del cliente.
  
BitLocker se implementa para OneDrive para la Empresa y SharePoint Online en todo el servicio. El cifrado por archivo también está en OneDrive para la Empresa y SharePoint Online en Microsoft 365 multiinquilino y en nuevos entornos dedicados basados en tecnología multiinquilino.
  
Mientras que BitLocker cifra todos los datos en un disco, el cifrado por archivo va más allá al incluir una clave de cifrado única para cada archivo. Además, la actualización de cada archivo se cifra mediante su propia clave de cifrado. Antes de almacenarse, las claves del contenido cifrado se almacenan en una ubicación físicamente independiente del contenido. Cada paso de este cifrado usa el Estándar de cifrado avanzado (AES) con claves de 256 bits y cumple el Estándar federal de procesamiento de información (FIPS) 140-2. El contenido cifrado se distribuye entre varios contenedores en el centro de datos y cada contenedor tiene credenciales exclusivas. Estas credenciales se almacenan en una ubicación física independiente del contenido o de las claves de contenido.
  
Para obtener información adicional sobre el cumplimiento de FIPS 140-2, vea [FIPS 140-2 Compliance](/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105)).
  
El cifrado de nivel de archivo en reposo saca provecho del almacenamiento de blobs para ofrecer aumento de almacenamiento prácticamente ilimitado y habilitar una protección sin precedentes. Todo el contenido de clientes en OneDrive para la Empresa y SharePoint Online se migrará al almacenamiento de blobs. A continuación, se muestra cómo se protegen los datos:
  
1. Todo el contenido se cifra, potencialmente con varias claves, y se distribuye por el centro de datos. Todos los archivos que se van a almacenar se dividen en uno o varios fragmentos, según su tamaño. A continuación, cada fragmento se cifra mediante su propia clave única. Las actualizaciones se administran de forma similar: el conjunto de cambios o diferencias, enviado por un usuario, se divide en fragmentos y cada uno se cifra con su propia clave.

2. Todos estos fragmentos (archivos, partes de archivos y diferencias de actualización) se almacenan como blobs en nuestro almacén de blobs. También se distribuyen aleatoriamente entre varios contenedores de blobs.

3. El "mapa" que se usa para volver a ensamblar el archivo a partir de sus componentes se almacena en la base de datos de contenido.

4. Cada contenedor de blobs tiene sus propias credenciales únicas por tipo de acceso (lectura, escritura, enumeración y eliminación). Cada conjunto de credenciales se encuentra en el almacén de claves seguras y se actualiza periódicamente.

En otras palabras, hay tres tipos diferentes de almacenes implicados en el cifrado por archivo en reposo, cada uno con una función distinta:
  
- El contenido se almacena como blobs cifrados en el almacén de blobs. La clave de cada fragmento de contenido se cifra y almacena por separado en la base de datos de contenido. El propio contenido no retiene ninguna pista sobre cómo se puede descifrar.

- La base de datos de contenido es una base de datos de SQL Server. Contiene el mapa necesario para localizar y volver a ensamblar todos los blobs de contenido que se encuentran en el almacén de blobs, así como las claves necesarias para descifrar esos blobs.

Cada uno de estos tres componentes de almacenamiento (el almacén de blobs, la base de datos de contenido y el almacén de claves) es físicamente independiente. La información contenida en cualquiera de los componentes es inutilizable por sí misma. Esto proporciona un nivel de seguridad sin precedentes. Sin acceso a los tres, es imposible recuperar las claves para los fragmentos, descifrar las claves para que puedan utilizarse, asociar las claves con sus fragmentos correspondientes, descifrar cualquier fragmento o reconstruir un documento a partir de sus fragmentos constituyentes.