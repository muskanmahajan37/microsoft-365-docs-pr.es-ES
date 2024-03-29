---
title: Empiece a usar las etiquetas de confidencialidad
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: ¿Se ha decidido a implementar etiquetas de confidencialidad para proteger los datos de su organización, pero no sabe por dónde empezar? Lea algunas instrucciones prácticas que le ayudarán a ponerse en marcha.
ms.openlocfilehash: 2e757f7f07dbb911a8d89890b1f1cce80d7247b5
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302117"
---
# <a name="get-started-with-sensitivity-labels"></a>Empiece a usar las etiquetas de confidencialidad

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Para obtener información sobre qué son las etiquetas de confidencialidad y cómo pueden ayudarle a proteger los datos de su organización, vea [Información sobre las etiquetas de confidencialidad](sensitivity-labels.md).

Si tiene [Azure Information Protection](/azure/information-protection/what-is-information-protection) y sigue usando etiquetas de Azure Information Protection administradas desde Azure Portal, deberá migrar estas etiquetas a la [plataforma de etiquetas unificada](/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform). En equipos con Windows, puede [elegir qué cliente de etiquetas desea usar](/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) para sus etiquetas de confidencialidad publicadas.

Cuando esté listo para empezar a proteger los datos de la organización mediante etiquetas de confidencialidad:

1. **Creación de las etiquetas.** Cree y asigne un nombre a las etiquetas de confidencialidad en función de la taxonomía de clasificación de su organización para distintos niveles de confidencialidad de contenido. Utilice nombres o términos comunes que tengan sentido para sus usuarios. Si aún no tiene una taxonomía establecida, considere la posibilidad de empezar por nombres de etiqueta como personal, público, general, confidencial y muy confidencial. Puede utilizar subetiquetas para agrupar etiquetas similares por categoría. Cuando se crea una etiqueta, use el texto de información sobre herramientas para ayudar a los usuarios a seleccionar la etiqueta apropiada.
    
    Para una guía más extensa para definir una taxonomía de clasificación, descargue el documento técnico "Clasificación de datos y taxonomía de etiquetas de confidencialidad" del [Portal de confianza de servicios](https://aka.ms/DataClassificationWhitepaper).

2. **Defina la función de cada etiqueta.** Configure los ajustes de protección que desea asociar a cada etiqueta. Por ejemplo, tal vez quiera que el contenido de menor confidencialidad (como una etiqueta "General") pueda simplemente tener un encabezado o pie de página aplicado, mientras que el contenido de mayor confidencialidad (como una etiqueta "Confidencial") debiera tener una marca de agua y encriptación.

3. **Publique las etiquetas.** Una vez configuradas las etiquetas de sensibilidad, publíquelas mediante una directiva de etiqueta. Decida qué usuarios y grupos deben tener las etiquetas y qué configuración de directiva usar. Una sola etiqueta es reutilizable: se define una vez y, después, se puede incluir en varias directivas de etiquetas asignadas a diferentes usuarios. Por ejemplo, puede crear una prueba de las etiquetas de confidencialidad asignando una directiva de etiqueta a solo algunos usuarios. Cuando esté listo para implementar las etiquetas en la organización, puede crear una nueva directiva para sus etiquetas y, esta vez, especificar todos los usuarios.

Flujo básico para la implementación y aplicación de etiquetas de confidencialidad:

![Diagrama que muestra el flujo de trabajo de las etiquetas de confidencialidad](../media/Sensitivity-label-flow.png)

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Requisitos de suscripción y licencias para las etiquetas de confidencialidad

Distintas suscripciones admiten diferentes etiquetas de confidencialidad y los requisitos de licencias para los usuarios dependen de las características que use.

Para ver las opciones para que los usuarios puedan beneficiarse de las características de cumplimiento de Microsoft 365, consulte la [Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance). Para las etiquetas de confidencialidad, vea la sección [Protección de la información](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) y la descarga relacionada de archivos PDF o Excel.

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>Permisos necesarios para crear y administrar etiquetas de confidencialidad

Los miembros de su equipo de cumplimiento que vayan a crear etiquetas de confidencialidad en el Centro de cumplimiento de Microsoft 365 o en el antiguo Centro de cumplimiento y seguridad. 

De forma predeterminada, los administradores globales de su espacio empresarial tienen acceso a estos centros de administración y pueden dar acceso a los oficiales de cumplimiento y a otras personas, sin darles todos los permisos de un administrador de espacio empresarial. Para este acceso administrativo limitado y delegado, agregue usuarios al grupo de roles **Administrador de datos de cumplimiento**, **Administrador de cumplimiento** o **Administrador de seguridad**. 

Como alternativa a los roles predeterminados, puede crear un nuevo grupo de roles y agregar los roles de **Administrador de etiquetas de confidencialidad** o **Configuración de la organización** a este grupo. Para un rol de solo lectura, utilice el **Lector de etiquetas de confidencialidad**. 

Para obtener instrucciones sobre cómo agregar usuarios a los roles predeterminados o crear sus propios grupos de roles, consulte [Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento de Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).

Estos permisos son necesarios solo para crear y configurar etiquetas de confidencialidad y sus directivas de etiquetado. No son necesarios para aplicar las etiquetas en aplicaciones o servicios. Si se necesitan permisos adicionales para configuraciones específicas relacionadas con las etiquetas de confidencialidad, estos permisos se especificarán en las instrucciones de la documentación correspondientes.

## <a name="deployment-strategy-for-sensitivity-labels"></a>Estrategia de implementación para las etiquetas de sensibilidad
Una estrategia exitosa para implementar etiquetas de carácter para una organización consiste en crear un equipo virtual de trabajo en el que se identifiquen y administren los requisitos técnicos de la empresa, pruebas de concepto, controles internos y aprobaciones, y implementación final para el entorno de producción.

Con la tabla de la siguiente sección, le recomendamos que identifique uno o dos escenarios principales que se correspondan con los requisitos empresariales más impactantes. Después de implementar estos escenarios, vuelva a la lista para identificar la siguiente o las dos prioridades para la implementación.

También encontrará instrucciones de implementación generales en la Guía de aceleración de implementación de Microsoft Information Protection y Prevención de pérdida de datos. Para obtener más información, vea la entrada del blog [Guía de aceleración de la Protección de la Información y el Cumplimiento de la Información de Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-365-information-protection-and-compliance-deployment/ba-p/2076404). 

## <a name="common-scenarios-for-sensitivity-labels"></a>Escenarios comunes de etiquetas de confidencialidad

Todos los escenarios requieren que [Crear y configurar etiquetas de confidencialidad y sus directivas](create-sensitivity-labels.md).

|Quiero...|Documentación|
|----------------|---------------|
|Administrar etiquetas de confidencialidad para las aplicaciones de Office para que el contenido se etiquete a medida que se crea (incluye la compatibilidad con el etiquetado manual en todas las plataformas) |[Administrar etiquetas de confidencialidad en las aplicaciones de Office](sensitivity-labels-office-apps.md)|
|Permitir que los usuarios etiqueten y protejan archivos de equipos Windows con las aplicaciones de Office, el Explorador de archivos y PowerShell|[Cliente de etiquetado unificado de Azure Information Protection para Windows](/azure/information-protection/rms-client/aip-clientv2)|
|Cifre documentos y mensajes de correo electrónico con etiquetas de confidencialidad y restrinja quién puede tener acceso a ellos y cómo puede usar el contenido |[Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](encryption-sensitivity-labels.md)|
|Habilite las etiquetas de confidencialidad para Office en la web, con soporte para coautoría, eDiscovery, la prevención de pérdida de datos y búsqueda, incluso cuando los documentos estén cifrados. | [Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)
|Usar la coautoría y guardar automáticamente en las aplicaciones de escritorio de Office cuando los documentos están cifrados | [Habilitar la coautoría para archivos cifrados con etiquetas de confidencialidad](sensitivity-labels-coauthoring.md)
|Aplicar automáticamente etiquetas de confidencialidad a documentos y mensajes de correo electrónico | [Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md)|
|Use etiquetas de confidencialidad para proteger el contenido de Teams y SharePoint |[Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](sensitivity-labels-teams-groups-sites.md)|
|Prevenir o advertir a los usuarios sobre el uso compartido de archivos o correos electrónicos con una etiqueta de confidencialidad específica |[Usar etiquetas de sensibilidad como condiciones en las directivas de DLP (versión preliminar)](dlp-sensitivity-label-as-condition.md) |
|Detecte, etiquete y proteja los archivos almacenados en almacenes de datos locales |[Implementación del escáner de Azure Information Protection para clasificar y proteger los archivos automáticamente](/azure/information-protection/deploy-aip-scanner)|
|Detecte, etiquete y proteja los archivos almacenados en almacenes de datos que están en la nube|[Descubrir, clasificar, etiquetar y proteger la información regulada y confidencialidad almacenada en la nube](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|Aplicar y ver las etiquetas de confidencialidad en Power BI y proteger los datos cuando se guarden fuera del servicio.|[Etiquetas de confidencialidad en Power BI](/power-bi/admin/service-security-sensitivity-label-overview)|
|Supervisar y comprender cómo se usan las etiquetas de confidencialidad en la organización|[Información general sobre la clasificación de datos](data-classification-overview.md) <br /><br /> [Introducción a la clasificación de datos](data-classification-overview.md)|
|Amplíe las etiquetas de confidencialidad a los servicios y aplicaciones de terceros.|[SDK de Microsoft Information Protection](/information-protection/develop/overview#microsoft-information-protection-sdk)|
|Amplíe las etiquetas de confidencialidad en todo el contenido de Azure Blob Storage, archivos de Azure, Azure Data Lake Storage Gen1 y Azure Data Lake Storage Gen12|[Etiquete automáticamente su contenido en Azure Purview](/azure/purview/create-sensitivity-label) |


## <a name="end-user-documentation-for-sensitivity-labels"></a>Documentación de usuario final para las etiquetas de confidencialidad

La documentación más eficaz para los usuarios finales serán la guía y las instrucciones que proporcione para los nombres de etiquetas y configuraciones que elija. Puede usar el valor de directiva de etiquetado **Proporcionar a los usuarios un vínculo a una página de ayuda personalizada** para especificar un vínculo interno para esta documentación. Así, los usuarios pueden acceder con facilidad desde el botón **Confidencialidad**:

- Para las etiquetas integradas: opción del menú **Más información**.
- Para el cliente de etiquetado unificado de Azure Information Protection: opción del menú **Ayuda y comentarios** > vínculo **Más información** en el cuadro de diálogo de Azure Information Protection.

Para escribir la documentación personalizada con mayor facilidad, consulte la siguiente entrada de blog para obtener un paquete de descarga que puede usar para entrenar a los usuarios e impulsar la adopción: [Formación de usuarios finales para las etiquetas de confidencialidad en M365: Cómo acelerar la adopción](https://techcommunity.microsoft.com/t5/microsoft-security-and/end-user-training-for-sensitivity-labels-in-m365-how-to/ba-p/1750880). 

También puede usar los siguientes recursos para obtener instrucciones básicas:

- [Aplicar etiquetas de confidencialidad a sus archivos y correos electrónicos en Office](https://support.microsoft.com/es-ES/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Problemas conocidos con las etiquetas de confidencialidad en Office](https://support.microsoft.com/es-ES/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Aplicar o recomendar automáticamente etiquetas de confidencialidad para sus archivos y correos electrónicos en Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Problemas conocidos al aplicar o recomendar automáticamente etiquetas de confidencialidad](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Guía del usuario de etiquetado unificado de Azure Information Protection](/azure/information-protection/rms-client/clientv2-user-guide)

Si las etiquetas de confidencialidad aplican el cifrado para documentos PDF, estos se pueden abrir con Microsoft Edge en Windows o Mac. Para obtener más información y para lectores alternativos, vea [¿Cuáles son los lectores de PDF compatibles para archivos PDF protegidos?](/azure/information-protection/rms-client/protected-pdf-readers#viewing-protected-pdfs-in-microsoft-edge-on-windows-or-mac)