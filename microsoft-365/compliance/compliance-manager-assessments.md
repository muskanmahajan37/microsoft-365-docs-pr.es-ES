---
title: Crear y administrar evaluaciones en El Administrador de cumplimiento de Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Cree evaluaciones en El Administrador de cumplimiento de Microsoft para ayudarle a cumplir los requisitos de normativas y certificaciones que son importantes para su organización.
ms.openlocfilehash: b8051a036f2ffda2f3a2840880318466a2ec71af
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500644"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>Crear y administrar evaluaciones en el Administrador de cumplimiento

**En este artículo:** Obtenga información sobre cómo personalizar el Administrador de cumplimiento para su organización mediante la creación y administración **de evaluaciones.** En este artículo se explica cómo crear evaluaciones, cómo organizarlas en  **grupos,** trabajar con **controles,** aceptar actualizaciones y exportar informes de **evaluación.**

> [!IMPORTANT]
> Las evaluaciones disponibles para su organización dependen del contrato de licencia. [Revise los detalles](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="introduction-to-assessments"></a>Introducción a las evaluaciones

El Administrador de cumplimiento le ayuda a administrar el cumplimiento de las evaluaciones de las normativas y certificaciones que se aplican a su organización. Las evaluaciones son agrupaciones de controles de un reglamento, estándar o directiva específicos. El Administrador de cumplimiento facilita el seguimiento de su cumplimiento proporcionando evaluaciones predefinidas que cubren una variedad de normativas y certificaciones regionales y del sector.

Cada evaluación se crea a partir de una [plantilla de evaluación](compliance-manager-templates.md). Las plantillas sirven como un marco que contiene los controles necesarios, las acciones de mejora y las acciones de Microsoft para completar la evaluación. Configurar las evaluaciones más relevantes para su organización puede ayudarle a implementar directivas y procedimientos operativos para limitar el riesgo de cumplimiento.

Todas las evaluaciones se enumeran en la página de evaluaciones. Obtenga más información [sobre cómo filtrar la vista de las evaluaciones](compliance-manager-setup.md#assessments-page)e interpretar los estados de estado .

## <a name="data-protection-baseline-default-assessment"></a>Evaluación predeterminada de línea base de protección de datos

Para empezar, Microsoft proporciona  una evaluación predeterminada en el Administrador de cumplimiento para la línea base de protección de datos de **Microsoft 365**. Esta evaluación de línea base tiene un conjunto de controles para los reglamentos y estándares clave para la protección de datos y el gobierno general de datos. Esta línea base se basa en elementos principalmente de NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Standardization), así como de FedRAMP (Federal Risk and Authorization Management Program) y GDPR (Reglamento general de protección de datos de la Unión Europea).

Esta evaluación se usa para calcular la puntuación de cumplimiento inicial la primera vez que se llega al Administrador de cumplimiento, antes de configurar cualquier otra evaluación. El Administrador de cumplimiento recopila las señales iniciales de las soluciones de Microsoft 365. Verá de un vistazo el rendimiento de su organización con respecto a los estándares y normativas clave de protección de datos y verá las acciones de mejora sugeridas que deben realizarse.

El Administrador de cumplimiento se vuelve más útil a medida que crea y administra sus propias evaluaciones para satisfacer las necesidades específicas de su organización.

## <a name="assessment-creation-overview"></a>Introducción a la creación de evaluaciones

Hay tres maneras de configurar evaluaciones:

1. [Use una evaluación predefinida](#use-a-pre-built-assessment).
2. [Extienda una evaluación predefinida para que se adapte a sus propias necesidades.](#extend-a-pre-built-assessment)
3. [Cree su propia evaluación personalizada](#create-your-own-custom-assessment).

> [!NOTE]
> Solo los usuarios que tienen un rol de administrador global, administración del administrador de cumplimiento o evaluador de administrador de cumplimiento pueden crear y modificar evaluaciones. Obtenga más información [sobre roles y permisos](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

**Usar una evaluación predefinida**

Inicia el recorrido de cumplimiento eligiendo una evaluación ya configurada por el Administrador de cumplimiento. Ofrecemos una amplia [](compliance-manager-templates.md) selección de plantillas para normativas y certificaciones que se alinean con industrias, regiones y estándares comunes de protección de datos, como RGPD e ISO 27001. Las plantillas contienen los controles y las acciones de mejora para ayudarle a cumplir los requisitos de una certificación determinada. Se le pedirá que elija una plantilla al empezar a [crear una evaluación](#use-a-pre-built-assessment).

**Ampliar una evaluación predefinida para que se adapte a sus necesidades**

Puede modificar una evaluación del Administrador de cumplimiento,un proceso al que nos referimos como "extensión", agregando sus propios controles y acciones para adaptarse mejor a las necesidades de su organización. Por ejemplo, si generalmente necesita cumplir con HIPAA pero requiere controles de seguridad o protección de datos adicionales, puede ampliar nuestra plantilla HIPAA agregando sus propios controles a ella. Vea las instrucciones para [ampliar una evaluación predefinida](#extend-a-pre-built-assessment).

**Crear su propia evaluación personalizada**

Puede crear su propia evaluación totalmente desde cero para realizar un seguimiento preciso de lo que necesita su organización. Crear su propia evaluación requiere que primero cree su propia plantilla para la evaluación en el Administrador de cumplimiento. Vea las instrucciones para [crear su propia evaluación personalizada.](#create-your-own-custom-assessment)

## <a name="understand-groups-before-creating-assessments"></a>Comprender grupos antes de crear evaluaciones

Antes de crear o modificar evaluaciones, es importante comprender cómo funcionan los grupos. Al crear una evaluación, deberá asignarla a un grupo durante el proceso. Por eso recomendamos planear una estrategia de agrupación para sus evaluaciones antes de crear evaluaciones.

### <a name="what-are-groups"></a>Qué son los grupos

Los grupos son contenedores que permiten organizar evaluaciones. Puede agrupar evaluaciones de una forma lógica, como por año o reglamento, o en función de las divisiones o geografías de su organización. A continuación se muestran ejemplos de dos grupos y sus evaluaciones subyacentes:

- **FFIEC IS assessment 2020**
  - FFIEC IS
- **Evaluaciones de privacidad y seguridad de datos**
  - ISO 27001:2013
  - ISO 27018:2014

Cuando dos evaluaciones diferentes del mismo grupo comparten acciones de mejora administradas por usted, las actualizaciones que realice en los detalles de implementación o el estado de una acción se sincronizarán automáticamente con la misma acción en cualquier otra evaluación del grupo. Esta sincronización le permite implementar una acción de mejora y cumplir varios requisitos en varias normativas.

### <a name="how-to-create-a-group"></a>Cómo crear un grupo

Se crea un grupo durante el proceso de [creación de una nueva evaluación](#to-create-an-assessment).

Los grupos no se pueden crear como entidades independientes. Un grupo debe contener al menos una evaluación. Para crear un grupo, primero debe crear una evaluación para colocarla en el grupo.

### <a name="what-to-know-when-working-with-groups"></a>Qué saber al trabajar con grupos

- Los nombres de grupo deben ser únicos en la organización.
- Los grupos no tienen propiedades de seguridad. Todos los permisos están asociados con evaluaciones.
- Una vez que agregue una evaluación a un grupo, no se podrá cambiar la agrupación.
- Los controles de evaluación relacionados en distintas evaluaciones dentro del mismo grupo se actualizan automáticamente cuando se completan.
- Si agrega una nueva evaluación a un grupo existente, la información común de las evaluaciones de ese grupo se copiará en la nueva evaluación.
- Los grupos pueden contener evaluaciones para la misma certificación o reglamento, pero cada grupo solo puede contener una evaluación para un par específico de certificación de productos. Por ejemplo, un grupo no puede contener dos evaluaciones para Office 365 y NIST CSF. Un grupo puede contener varias evaluaciones para el mismo producto solo si la certificación o regulación correspondientes para cada uno es diferente.
- Al eliminar una evaluación, se rompe la relación entre esa evaluación y el grupo.
- Los grupos no se pueden eliminar.
- Cuando se realiza un cambio en una mejora que aparece en varios grupos, ese cambio se refleja en todos los casos de esa acción de mejora.

## <a name="use-a-pre-built-assessment"></a>Usar una evaluación predefinida

Hay dos puntos de partida para crear una evaluación a partir de una plantilla del Administrador de cumplimiento.

Puede comenzar el proceso desde la página  de evaluaciones seleccionando el botón Agregar evaluación y, a continuación, trabajando en el asistente para la creación de evaluaciones. A continuación se indican los pasos para este proceso.

También puede empezar desde la página de plantillas de evaluación buscando la plantilla que desee y seleccionándose en la lista para llegar a su página de detalles. En la página de detalles de la plantilla, seleccione **Crear evaluación**. A continuación, escribirás el asistente con la plantilla ya seleccionada.

### <a name="to-create-an-assessment"></a>Para crear una evaluación

1. Sepa a qué grupo asignará la evaluación o estará preparado para crear uno nuevo para esta evaluación. [Obtenga más información sobre grupos](#understand-groups-before-creating-assessments).  

2. Vaya a la **página evaluaciones** del Administrador de cumplimiento y seleccione **Agregar evaluación.** Aparecerá un asistente de evaluación en un panel desplegable grande.

3. **Seleccione una plantilla:** elija una plantilla para que sirva de base para su evaluación. Verá la lista de plantillas divididas en categorías incluidas y premium (vea [Tipos de plantilla](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) para obtener más información). Seleccione el botón de radio junto a la plantilla elegida y, a continuación, **seleccione Siguiente**.

4. **Nombre y grupo:** Escriba un nombre para la evaluación en el **campo Nombre de evaluación.** Los nombres de evaluación deben ser únicos dentro de los grupos. Si el nombre de la evaluación coincide con el nombre de otra evaluación en un grupo determinado, recibirá un error que le pedirá que cree un nombre diferente.

5. Asigne la evaluación a un grupo. Puede:
    - Seleccione **Usar grupo existente** para asignarlo a un grupo que ya ha creado; o
    - Seleccione **Crear nuevo grupo** para crear un nuevo grupo y asígnele esta evaluación:
        - Determina un nombre para el grupo y escribelo en el campo debajo del botón de radio.
        - Puede copiar **datos de un grupo existente,** como detalles y documentos de implementación y pruebas, seleccionando los cuadros correspondientes.

    Cuando haya terminado, seleccione **Siguiente**.

6. **Revisar y finalizar:** La última pantalla del asistente muestra la plantilla, el nombre y el grupo elegidos para la evaluación. Puede editar cualquiera de estas opciones desde los vínculos de la pantalla, que le llevan de nuevo a los pasos relevantes del asistente. Cuando esté listo, seleccione **Crear evaluación**.

7. En la siguiente pantalla se confirma que ha creado correctamente la nueva evaluación. Seleccione **Listo** para cerrar el asistente y la página de detalles de la nueva evaluación aparecerá en la pantalla.

Si ve una pantalla **Error de** evaluación después de seleccionar **Crear** evaluación, seleccione **Volver** a intentar volver a crear la evaluación.

Puede cambiar el nombre de la evaluación después  de crearla seleccionando el botón Editar nombre en la esquina superior derecha de la página de detalles [de la evaluación.](#monitor-assessment-progress-and-controls)

## <a name="extend-a-pre-built-assessment"></a>Extender una evaluación predefinida

Puede modificar una evaluación predefinida agregando sus propios controles y acciones de mejora a la plantilla de la evaluación. Este proceso se denomina "extensión de una plantilla de Microsoft" en el Administrador de cumplimiento. Cuando amplíe la plantilla de una evaluación, recibirá las actualizaciones publicadas por Microsoft, que pueden producirse cuando haya cambios en el producto o la regulación relacionada (vea [Accepting updates to assessments](#accepting-updates-to-assessments)).

Para completar este proceso, empiece en la página **de** plantillas de evaluación en lugar de en la página **de evaluaciones.**

**Antes de empezar**

Para prepararse para este proceso, primero deberá ensamblar una hoja de cálculo de Excel con un formato especial para importar los datos de plantilla necesarios. Existen requisitos especiales para los archivos [de Excel con formato usados](compliance-manager-templates.md#formatting-your-template-data-with-excel) en el proceso de extensión. Vea estos puntos adicionales para ayudar a evitar errores en el proceso de importación:

- La hoja de cálculo solo debe contener las acciones y controles que desee agregar a la evaluación. 
- La hoja de cálculo no puede contener ninguno de los controles o acciones que ya existen en la evaluación que desea modificar.
- Considere la posibilidad de incluir "extensión" en el título de la plantilla, por ejemplo, "RGPD – extensión [nombre de la empresa]". Esto facilita la identificación en la  lista de la página plantillas de evaluación como distinta de la plantilla estándar proporcionada por Microsoft o una plantilla personalizada con un nombre similar.

Después de dar formato a la hoja de cálculo, siga los pasos siguientes.

**Pasos para ampliar una plantilla del Administrador de cumplimiento**

1. Vaya a la **página Plantillas de evaluación** y seleccione Crear nueva **plantilla.** Se abrirá un asistente para la creación de plantillas.

2. Elija el tipo de plantilla que desea crear. En este caso, seleccione **Extender una plantilla de Microsoft** y, a continuación, Seleccionar plantilla de **Microsoft**.

3. Aparece un panel desplegable de selección de plantilla en el lado derecho de la pantalla, que muestra una lista de todas las plantillas y su estado de activo o inactivo. El **contador de plantillas** activadas muestra cuántas plantillas están actualmente en uso del número total disponible para usar. Si supera el límite, una barra de mensajes le proporcionará aviso. Vea [Tipos de plantilla](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) para obtener más información.

4. Aparece un panel desplegable de selección de plantilla en el lado derecho de la pantalla. Usar **la** búsqueda para aplicar filtros para localizar la plantilla que desee

5. Una vez que encuentre la plantilla, seleccione el botón de radio situado a la izquierda de su nombre y, a continuación, **seleccione Guardar**.

6. En la siguiente pantalla se muestra la plantilla seleccionada. Si es correcto, seleccione **Siguiente**. (Si es incorrecto, **elija Seleccionar una plantilla diferente** para volver a elegir).

7. En la **pantalla Cargar archivo,** seleccione **Examinar** para buscar y cargar el archivo de Excel con formato que contiene todos los datos de plantilla necesarios.

8. Si no hay ningún problema con el archivo, en la siguiente pantalla se muestra el nombre del archivo cargado. Seleccione **Siguiente** para continuar (si necesita cambiar el archivo, seleccione **Cargar un archivo diferente**).

    - Si hay un problema con el archivo, un mensaje de error en la parte superior explica lo que está mal. Tendrás que corregir y volver a cargar el archivo. Los errores se producen si la hoja de cálculo tiene un formato incorrecto o si hay información no válida en determinados campos.
 
9. La **pantalla Revisar y finalizar** muestra el número de acciones y controles de mejora y la puntuación máxima de la plantilla. Cuando esté listo para aprobar, seleccione **Siguiente**. (Si necesita realizar cambios, seleccione **Cargar un archivo diferente**.)

10. La última pantalla confirma que se ha creado una plantilla nueva. Seleccione **Listo** para salir del asistente.

11. Llegarás a la página de detalles de la nueva plantilla. Desde aquí puede crear su evaluación seleccionando **Crear evaluación**. Para obtener instrucciones, comience en el paso #4 en las instrucciones [de creación de evaluaciones anteriores](#to-create-an-assessment).

## <a name="create-your-own-custom-assessment"></a>Crear su propia evaluación personalizada

Crear una evaluación personalizada en el Administrador de cumplimiento requiere que cree su propia plantilla. Para crear su propia plantilla, primero ensamblará una hoja de cálculo de Excel con formato para importar los datos de plantilla necesarios. También ayuda a decidir con antelación a qué grupo asignará la evaluación al crearla (obtenga más información sobre [los grupos).](#what-are-groups)

**Siga los pasos siguientes para crear la evaluación personalizada:**

1. **Dar formato al archivo de Excel.** Comience por dar formato a los datos de la plantilla en una hoja de cálculo de Excel con [estas instrucciones](compliance-manager-templates.md#formatting-your-template-data-with-excel).

2. **Cree la plantilla** siguiendo [estas instrucciones](compliance-manager-templates.md#create-a-new-template).

3. **Cree la evaluación a** partir de la plantilla. Para empezar, abra la página de detalles de la plantilla  y seleccione **Crear** evaluación, o vaya a la página de evaluaciones y seleccione **Crear evaluación.**

4. Un asistente para la creación de evaluaciones aparecerá en un panel desplegable grande. Desde aquí, puede seguir las instrucciones que comienzan en el paso #3 las instrucciones de creación de [evaluaciones,](#to-create-an-assessment)usando la nueva plantilla personalizada para su evaluación.

## <a name="delete-an-assessment"></a>Eliminar una evaluación

Al eliminar una evaluación, se elimina de la lista de la página de evaluaciones. Tenga en cuenta estos puntos importantes sobre la eliminación de evaluaciones:

- **Eliminar una evaluación es permanente; no se puede recuperar.** Si desea volver a usar la misma evaluación, tendrá que volver a crearla.
- Si las acciones de mejora de la evaluación no aparecen en ninguna otra evaluación, se eliminarán cuando se elimine la evaluación.
- Se recomienda [exportar un informe de](#export-an-assessment-report) la evaluación antes de eliminarlo de forma permanente.

Para eliminar una evaluación, siga los pasos siguientes:

1. En la **página de evaluaciones,** seleccione la evaluación que desea eliminar para abrir la página de detalles de esa evaluación.

2. Seleccione **Eliminar evaluación** en la esquina superior derecha de la pantalla.

3. Aparecerá una ventana que le pedirá que confirme que desea eliminar permanentemente la evaluación. Seleccione **Eliminar evaluación** para cerrar la ventana. Recibirá una ventana de confirmación de que la evaluación se eliminó del Administrador de cumplimiento.

Si elimina la única evaluación de un grupo, ese grupo también se elimina del Administrador de cumplimiento.

> [!NOTE]
> No puede eliminar todas las evaluaciones. Las organizaciones necesitan al menos una evaluación para que el Administrador de cumplimiento funcione correctamente. Si la evaluación que desea eliminar es la única, agregue otra evaluación antes de eliminar la otra evaluación.

## <a name="monitor-assessment-progress-and-controls"></a>Supervisar el progreso y los controles de evaluación

Cada evaluación tiene una página de detalles que ofrece una vista de un vistazo del progreso en la finalización de la evaluación. La página muestra el progreso en la finalización de los controles y el estado de prueba de las acciones clave de mejora dentro de esos controles.

### <a name="overview-tab"></a>Ficha Información general

La pestaña información general contiene un gráfico que muestra el porcentaje hacia la finalización de la evaluación. Este gráfico contiene un desglose de puntos de acciones de su propiedad y puntos de acciones propiedad de Microsoft, por lo que puede ver cuántos puntos más necesita para completar la evaluación.

Las principales acciones de mejora para los controles de la evaluación se enumeran en orden de mayor impacto potencial para ganar puntos. El gráfico asociado detalla el estado de las pruebas agregadas de las acciones de mejora para que pueda medir rápidamente lo que se ha probado y lo que aún debe hacerse.

Para obtener acceso a acciones de mejora individuales, visita la **pestaña Controles** o la pestaña Tus **acciones de** mejora.

### <a name="controls-tab"></a>Pestaña Controles

La pestaña controles muestra información detallada para cada control asignado a la evaluación. Un **gráfico de desglose de** estado de control muestra el estado de los controles por familia, por lo que puede ver de un vistazo qué agrupaciones de controles necesitan atención.

Debajo del gráfico, una tabla enumera información detallada sobre cada control dentro de la evaluación. Los controles se agrupan por familia de controles. Expanda cada nombre de familia para mostrar los controles individuales que contiene. La información enumerada para cada control incluye:

- **Título del control**
- **Estado:** refleja el estado de prueba de las acciones de mejora dentro del control 
    - **Pasado:** todas las acciones de mejora tienen un estado de prueba de "pasado", o al menos se pasa una y el resto está "fuera del ámbito"
    -  **Error:** al menos una acción de mejora tiene un estado de prueba de "error"
    - **Ninguno:** no se han probado todas las acciones de mejora
    - **Fuera del ámbito:** todas las acciones de mejora están fuera del ámbito de esta evaluación
    - **En curso:** las acciones de mejora tienen un estado distinto de los enumerados anteriormente, que podría incluir "en curso", "crédito parcial" o "no detectado"
- **Identificador de** control: número de identificación del control, asignado por su reglamento, estándar o directiva correspondientes
- **Puntos logrados:** el número de puntos ganados al completar acciones, del número total de puntos alcanzables 
- **Tus acciones:** el número de acciones completadas fuera del número total de acciones que se realizarán
- **Acciones de Microsoft:** el número de acciones completadas por Microsoft 

Para ver los detalles de un control, selecciónelo en su fila de la tabla. La página de detalles del control muestra un gráfico que indica el estado de prueba de las acciones dentro de ese control. Una tabla debajo del gráfico muestra acciones clave de mejora para ese control.

Seleccione una acción de mejora de la lista para profundizar en la página de detalles de la acción de mejora. Las páginas de detalles muestran el estado de la prueba, las notas de implementación y el inicio en la solución recomendada.

### <a name="your-improvement-actions-tab"></a>Pestaña Acciones de mejora

La pestaña de las acciones de mejora enumera todos los controles de la evaluación que administra la organización. La barra de estado detalla el estado agregado de las acciones de mejora en la evaluación para que pueda medir rápidamente lo que se ha probado y lo que aún debe hacerse. Debajo de la barra se encuentra la lista completa de acciones de mejora y detalles clave, incluidos: estado de prueba, número de puntos potenciales y ganados, normativas y estándares asociados, solución aplicable, tipo de acción y familia de controles. Obtenga más información sobre [cómo contribuyen las acciones a la puntuación de cumplimiento](compliance-score-calculation.md#action-types-and-points).

Seleccione una acción de mejora para ver su página de detalles y seleccione **el** vínculo Iniciar ahora para abrir la solución para realizar acciones.

### <a name="microsoft-actions-tab"></a>Pestaña Acciones de Microsoft

La pestaña Acciones de Microsoft enumera todas las acciones de la evaluación administradas por Microsoft. La lista muestra detalles de acción clave, incluidos: estado de prueba, puntos que contribuyen a la puntuación general de cumplimiento, normativas y estándares asociados, solución aplicable, tipo de acción y familia de controles. Seleccione una acción de mejora para ver su página de detalles.

Obtenga más información sobre cómo se realiza un seguimiento y una puntuación de los controles [y las acciones de mejora.](compliance-score-calculation.md)

## <a name="accepting-updates-to-assessments"></a>Aceptar actualizaciones de evaluaciones

Cuando una actualización esté disponible para una evaluación, verá una notificación y tendrá la opción de aceptar la actualización o aplazar la actualización más adelante.

### <a name="what-causes-an-update"></a>Qué causa una actualización

Una actualización de evaluación se produce cuando hay cambios de plantilla subyacentes que afectan a la puntuación. Los cambios pueden implicar ajustar la asignación de control u otras instrucciones basadas en cambios normativos o cambios en el producto. Las actualizaciones de evaluación pueden originarse desde su organización (por ejemplo, cuando se modifica una [plantilla personalizada)](compliance-manager-templates.md#modify-a-template)así como desde Microsoft.

Si Microsoft actualiza una plantilla del Administrador de cumplimiento que extendió, la evaluación heredará dichas actualizaciones una vez que las acepte. La evaluación conservará los atributos adicionales que aplicó a la evaluación cuando la extendió.

Las evaluaciones personalizadas que cree no reciben actualizaciones de plantillas de Microsoft. Las evaluaciones personalizadas pueden recibir actualizaciones de acciones de mejora, pero las actualizaciones de Microsoft para controlar la asignación entre evaluaciones y acciones de mejora no se aplican a plantillas personalizadas.

> [!NOTE]
> Las actualizaciones de las evaluaciones solo se aplican en el nivel de grupo. Si tiene dos evaluaciones creadas a partir de la misma plantilla que existen en dos grupos diferentes, cada evaluación tendrá una notificación de actualización pendiente y deberá aceptar la actualización de cada evaluación en su grupo respectivo individualmente.

#### <a name="where-youll-see-assessment-update-notifications"></a>Dónde verá las notificaciones de actualización de evaluación

La página de detalles de la evaluación también muestra **una etiqueta de actualización** pendiente junto a la evaluación con una actualización. Seleccione esa evaluación para ir a su página de detalles.

Un mensaje cerca de la parte superior de la página de detalles de la evaluación muestra que hay una actualización disponible para esa evaluación. Seleccione el **botón Revisar actualización** en el banner para revisar los cambios específicos y aceptar o aplazar la actualización.

La página de detalles de la evaluación también puede enumerar las acciones de mejora que tienen una **etiqueta de actualización** pendiente junto a ellas. Estas actualizaciones son para cambios específicos en las propias acciones de mejora y deben aceptarse por separado. Visita [Aceptar actualizaciones para acciones de mejora](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions) para obtener más información.

#### <a name="review-update-to-accept-or-defer"></a>Revisar la actualización para aceptar o aplazar

Después de seleccionar **Revisar actualización en** la página detalles de la evaluación, aparece un panel desplegable en el lado derecho de la pantalla. El panel desplegable proporciona los detalles clave siguientes sobre la actualización pendiente:

- El título de la plantilla
- Origen de la actualización (Microsoft, su organización o un usuario específico)
- La fecha en que se creó la actualización
- Información general que explica la actualización
- Detalles específicos sobre los cambios, incluido el impacto en la puntuación de cumplimiento, la cantidad de progreso hacia la finalización de la evaluación y el número específico de cambios en las acciones y controles de mejora.

Al seleccionar el **vínculo Plantilla** actualizada, se descargará un archivo de Excel que contenga datos de control para la versión de la plantilla con las actualizaciones pendientes. Al seleccionar el **vínculo Plantilla actual,** se descarga un archivo de la plantilla existente sin los cambios.

Para aceptar la actualización y realizar los cambios en la evaluación, seleccione **Aceptar actualización**. Los cambios aceptados son permanentes.

Si selecciona **Cancelar,** la actualización no se aplicará a la evaluación. Sin embargo, seguirás consultando la notificación **De actualización** pendiente hasta que aceptes la actualización.

**Por qué se recomienda aceptar actualizaciones**

La aceptación de actualizaciones ayuda a garantizar que tenga las instrucciones más actualizadas sobre el uso de soluciones y la toma de las acciones de mejora adecuadas para ayudarle a cumplir los requisitos de la certificación en la mano.

**Por qué es posible que quieras aplazar una actualización**

Si está en medio de completar una evaluación, es posible que desee asegurarse de que ha terminado de trabajar en ella antes de aceptar una actualización de la evaluación que podría interrumpir la asignación de control. Puede aplazar la actualización más adelante **seleccionando Cancelar** en el panel desplegable de la actualización de revisión.

## <a name="export-an-assessment-report"></a>Exportar un informe de evaluación

Puede exportar una evaluación a un archivo de Excel para las partes interesadas en el cumplimiento de la organización o para auditores y reguladores externos. En la página de detalles de la evaluación, seleccione el botón **Generar** informe cerca de la parte superior de la página, que crea un archivo de Excel que puede guardar y compartir.

El informe es una instantánea de la evaluación a partir de la fecha y hora de la exportación. Contiene los detalles de los controles administrados por usted y Microsoft, incluidos el estado de implementación, la fecha de prueba y los resultados de la prueba.