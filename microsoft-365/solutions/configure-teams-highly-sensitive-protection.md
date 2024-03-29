---
title: Configuración de equipos con protección de datos con un nivel de confidencialidad alto
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
recommendations: false
description: Obtenga información sobre cómo implementar equipos con la protección de datos con un nivel de confidencialidad alto.
ms.openlocfilehash: 7c5485a008434b351eebbec3ea1f20b10d82278a
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583693"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a>Configuración de equipos con protección de datos con un nivel de confidencialidad alto

En este artículo, observamos la configuración de un equipo con un nivel de protección de confidencialidad alta. Asegúrese de que ha completado los pasos descritos en [Implementar equipos con la protección de línea base](configure-teams-baseline-protection.md) antes de seguir los pasos de este artículo.

Para este nivel de protección, se crea una etiqueta de sensibilidad que puede usarse en toda la organización para los equipos y archivos altamente confidenciales. Solo los miembros de su organización y los invitados que haya especificado podrán descifrar los archivos que usen esta etiqueta. Si tiene que aislar aún más los permisos para que solo los miembros de un equipo específico puedan descifrar los archivos, consulte [Implementación de un equipo con aislamiento de seguridad](secure-teams-security-isolation.md).

El nivel de confidencialidad alto ofrece las siguientes protecciones adicionales al nivel de línea base:

- Una etiqueta de confidencialidad para el equipo que le permite activar o desactivar el uso compartido de invitado y bloquea el acceso a contenido de SharePoint para dispositivos no administrados. Esta etiqueta también se puede usar para clasificar y cifrar archivos.
- Un tipo de vínculo para compartir predeterminado más restrictivo
- Solo los propietarios del equipo podrán crear canales privados.
- Las solicitudes de acceso para el sitio de SharePoint asociado están desactivadas.

## <a name="guest-sharing"></a>Uso compartido de invitados

Según la naturaleza de su empresa, es posible que quiera habilitar o no el uso compartido de invitados para equipos que contienen datos con un nivel de confidencialidad alto. Si tiene previsto colaborar con personas ajenas a su organización en el equipo, le recomendamos que habilite el uso compartido de invitados. Microsoft 365 incluye una variedad de características de seguridad y cumplimiento para ayudarle a compartir contenido confidencial de forma segura. Por lo general, se trata de una opción más segura que enviar correo directamente a las personas de fuera de su organización.

Para más información sobre el uso compartido de invitados de forma segura, vea los recursos siguientes:

- [Limitar la exposición accidental de archivos al compartirlos con usuarios externos a la organización](./share-limit-accidental-exposure.md)
- [Crear un entorno seguro de uso compartido para invitados](./create-secure-guest-sharing-environment.md)

Para permitir o bloquear el uso compartido de invitados, utilizamos una combinación de una etiqueta de confidencialidad para el equipo y controles de uso compartido a nivel de sitio para el sitio de SharePoint asociado, ambos tratados más adelante.

## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Para el nivel de protección de confidencialidad alta, usaremos una etiqueta de confidencialidad para clasificar al equipo. Esta etiqueta también se puede usar para clasificar y cifrar archivos individuales en este o en otros equipos, o en otras ubicaciones de archivo como SharePoint o OneDrive. 

Como primer paso, debe habilitar las etiquetas de confidencialidad para los equipos. Consulte [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, los grupos de Microsoft 365 y los sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md) para más información.

Si ya tiene las etiquetas de confidencialidad implementadas en la organización, tenga en cuenta que se adapta a la estrategia general de etiquetas. Si es necesario, puede cambiar el nombre o la configuración para satisfacer las necesidades de su organización.

Cuando haya habilitado las etiquetas de confidencialidad para Teams, el siguiente paso es crear la etiqueta.

Crear una etiqueta de confidencialidad
1. Abra el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com).
2. En **Soluciones**, haga clic en **Protección de la información**.
3. Haga clic en **Crear una etiqueta**.
4. Asigne un nombre a la etiqueta. Le sugerimos **Confidencialidad alta**, pero puede elegir otro nombre si ya está en uso.
5. Escriba un nombre y una descripción para el complemento y, a continuación, haga clic en **Siguiente**.
6. En la página **Definir el ámbito de la página de la etiqueta**, seleccione **Archivos & mensajes de correo electrónico** y **Grupos & sitios** y haga clic en **Siguiente**.
7. Luego, en la página **Elegir la configuración de protección para archivos y mensajes de correo electrónico**, asegúrese de seleccionar **Cifrar archivos y mensajes de correo electrónico** luego haga clic en **Siguiente**.
8. En la página **Cifrado**, elija **Configurar opciones de cifrado**.
9. En **Asignar permisos a usuarios y grupos específicos**, haga clic en **Asignar permisos**.
10. Haga clic en **Agregar todos los usuarios y grupos de su organización**.
11. Si existen invitados que deben tener permisos para descifrar los archivos, haga clic en **Agregar usuarios o grupos** y agréguelos.
12.  Haga clic en **Guardar** y después en **Siguiente**.
13. En la página *Etiquetado automático para archivos y mensajes de correo electrónico**, haga clic en **Siguiente**.
14. En la página **Definir la configuración de protección de los sitios y grupos**, seleccione **Configuración de privacidad y acceso de usuarios externo** y **Configuración de acceso de dispositivo y uso compartido externo** y haga clic en **Siguiente**.
15. En la página **Definir privacidad y acceso a usuarios externos**, en **Privacidad**, seleccione la opción **Privado**.
16. Si desea permitir el acceso de invitado, en **Acceso de usuarios externos**, seleccione **Permitir que los propietarios del grupo de Microsoft 365 agreguen personas de fuera de su organización al grupo como invitados**.
17. Haga clic en **Siguiente**.
18. En la página **Definir el uso compartido externo y el acceso al dispositivo**, seleccione **Controlar el uso compartido externo en sitios de SharePoint etiquetados**.
19. En **El contenido se puede compartir con**, elija **Invitados nuevos y existentes** si va a permitir el acceso de invitado o **Solo los usuarios de su organización** en caso contrario.
20. En **Equipos no administrados**, elija **Bloquear el acceso**. (Si está permitiendo invitados y no tienen dispositivos administrados, es posible que quiera elegir **Permitir acceso limitado, solo Web**).
21. Haga clic en **Siguiente**.
22. En la página **Etiquetado automático para las columnas de la base de datos**, haga clic en **Siguiente**.
23. Haga clic en **Crear etiqueta** y después en **Listo**.

Una vez que haya creado la etiqueta, debe comunicarla a los usuarios que la van a usar. Para la protección confidencial, haremos que la etiqueta esté disponible para todos los usuarios. Publique la etiqueta en el Centro de cumplimiento de Microsoft 365, en la pestaña **Directivas de etiqueta** de la página **Protección de la información**. Si tiene una directiva existente que se aplica a todos los usuarios, agregue esta etiqueta a esa directiva. Si necesita crear una directiva nueva, vea [Publicar etiquetas de confidencialidad creando una directiva de etiqueta](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).

## <a name="create-a-team"></a>Crear un equipo

La configuración adicional del escenario de confidencialidad alta se hace en el sitio de SharePoint asociado al equipo, por lo que el siguiente paso es crear un equipo.

Para crear un equipo para información con un nivel de confidencialidad alto
1. En Teams, haga clic en **Teams** en el lado izquierdo de la aplicación, luego haga clic en **Unirse o crear un equipo** en la parte inferior de la lista de equipos.
2. Haga clic en **Crear equipo** (primera tarjeta, esquina superior izquierda).
3. Elija **Crear un equipo desde cero**.
4. En la lista **Confidencialidad**, elija la etiqueta **Confidencialidad alta** que acaba de crear.
5. En **Privacidad**, haga clic en **Privado**.
6. Escriba un nombre para el equipo y haga clic en **Crear**.
7. Agregue usuarios al equipo y, después, haga clic en **Cerrar**.

## <a name="private-channel-settings"></a>Configuración de canal privado

En este nivel, restringimos la creación de canales privados a los propietarios del equipo.

Para restringir la creación de un canal privado
1. En el equipo, haga clic en **Más opciones** y después en **Administrar equipo**.
2. En la pestaña **Configuración**, expanda **Permisos de los miembros**.
3. Desactive la casilla de verificación **Permitir a los miembros crear canales privados**.

También puede usar [Directivas de equipos](/MicrosoftTeams/teams-policies) para controlar quién puede crear canales privados.

## <a name="sharepoint-settings"></a>Configuración de SharePoint

Cada vez que cree un nuevo equipo con la etiqueta de confidencialidad alta, debe realizar dos pasos en SharePoint:

- Actualice la configuración de uso compartido de invitado para el sitio en el Centro de administración de SharePoint para que actualizar el vínculo de uso compartido predeterminado para *Usuarios con acceso existente*.
- Actualice la configuración de uso compartido del sitio en el propio sitio para evitar que los miembros compartan los archivos, las carpetas o el sitio, y desactivar las solicitudes de acceso.

### <a name="site-default-sharing-link-settings"></a>Configuración del vínculo para compartir predeterminado del sitio

Para actualizar el tipo de vínculo para compartir predeterminado del sitio

1. Abra el [Centro de administración de SharePoint](https://admin.microsoft.com/sharepoint).
2. En **Sitios**, haga clic en **Sitios activos**.
3. Haga clic en el sitio que está asociado al equipo.
4. En **Uso compartido externo** de la pestaña **Directivas**, haga clic en **Editar**.
5. En Tipo de vínculo de uso compartido predeterminado, desactive la casilla de verificación **Igual que la configuración de nivel de organización** y seleccione **Usuarios con acceso existente**.
6. Haga clic en **Guardar**.

#### <a name="private-channels"></a>Canales privados

Si agrega canales privados al equipo, cada canal privado crea un sitio de SharePoint nuevo con la configuración de uso compartido predeterminada. Estos sitios no están visibles en el Centro de administración de SharePoint, por lo que debe usar el cmdlet Set-SPOSite de PowerShell para actualizar la configuración de uso compartido de invitado.

### <a name="site-sharing-settings"></a>Configuración de uso compartido del sitio 

Para ayudar a garantizar que el sitio de SharePoint no se comparta con personas que no son miembros del equipo, limitamos dicho uso compartido a los propietarios. También limitamos el uso compartido de archivos y carpetas a los propietarios del equipo. Esto permite asegurar que los propietarios son conscientes siempre que se comparte un archivo con alguien ajeno al equipo.

Para configurar el uso compartido del sitio solo para propietarios
1. En Teams, vaya a la pestaña **General** del equipo que quiere actualizar.
2. En la barra de herramientas del equipo, haga clic en **Archivos**.
3. Haga clic en los puntos suspensivos y, luego, en **Abrir en SharePoint**.
4. En la barra de herramientas, haga clic en el sitio de SharePoint subyacente, en el icono de configuración y, luego, en **Permisos del sitio**.
5. En el panel **Permisos del sitio**, en **Uso compartido del sitio**, haga clic en **Cambiar cómo pueden compartir los miembros**.
6. En **Permisos de uso compartido**, seleccione **Solo los propietarios del sitio pueden compartir archivos, carpetas y el sitio**.
7. Establezca **Permitir solicitudes de acceso** en **Desactivado** y, después, haga clic en **Guardar**.

## <a name="see-also"></a>Consulte también

[Crear y configurar etiquetas de confidencialidad y sus directivas](../compliance/create-sensitivity-labels.md)
