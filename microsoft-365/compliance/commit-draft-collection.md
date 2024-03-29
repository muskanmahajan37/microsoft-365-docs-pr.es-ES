---
title: Confirmar un borrador de colección en un conjunto de revisión
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Después de crear e iterar en una colección borrador, puede confirmarla en un conjunto de revisión. Cuando se confirma un borrador de colección, los elementos recopilados se agregan al conjunto de revisión en el caso. Después de que los elementos recopilados estén en el conjunto de revisión, puede analizarlos, revisarlos y exportarlos.
ms.openlocfilehash: e28592e7aac289bfc0cc29d312963fa21d9f8fd4
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838951"
---
# <a name="commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery"></a>Confirmar un borrador de colección en un conjunto de revisión en exhibición de documentos electrónicos avanzada

Cuando esté satisfecho con los elementos que haya recopilado en una colección borrador y esté listo para analizarlos, etiquetarlos y revisarlos, puede agregar una colección a un conjunto de revisión en el caso. Cuando se confirma un borrador de colección en un conjunto de revisión, los elementos recopilados se copian desde su ubicación de contenido original en Microsoft 365 a un conjunto de opiniones. Un conjunto de revisión es una ubicación segura de Azure Storage proporcionada por Microsoft en la nube de Microsoft.

## <a name="commit-a-draft-collection-to-a-review-set"></a>Confirmar un borrador de colección en un conjunto de revisión

1. En el Centro de cumplimiento de Microsoft 365, abra el caso eDiscovery avanzado y, a continuación, seleccione la pestaña **Colecciones** para mostrar una lista de las colecciones en el caso.

   ![Lista de colecciones en un caso](../media/CommitDraftCollections1.png)

   > [!TIP]
   > Un valor de en la columna Estado identifica las colecciones de borrador que se pueden `Estimated` agregar a un conjunto de revisión.  Un estado de indica que ya se ha agregado una colección `Committed` a un conjunto de revisión.

2. En la **página Colecciones,** seleccione el borrador de colección que desea confirmar en un conjunto de revisión.

3. En la parte inferior de la página desplegable, seleccione **Acciones**  >  **Editar colección**.

4. En el Asistente para editar colección, haga clic **en Siguiente** hasta que se muestre **la página** Guardar borrador o recopilar.

5. Configure las siguientes opciones:

   1. Seleccione **Recopilar elementos y agregar al conjunto de revisión**.

   2. Decida si desea agregar la colección a un nuevo conjunto de revisión (que se crea después de enviar la colección) o a un conjunto de revisión existente. Complete esta sección en función de su decisión.

   3. Configure las opciones de colección adicionales:

       - Mensajes de Teams y **Yammer:** seleccione esta opción para agregar subprocesos de conversación a la colección que incluyan los elementos de chat devueltos por la consulta de búsqueda en la colección. Esto significa que se reconstruye la conversación de chat que contiene elementos que coinciden con los criterios de búsqueda. Esto te permite revisar los elementos de chat en el contexto de la conversación de ida y vuelta. Para obtener más información, vea [Subprocesos de conversación en eDiscovery avanzado](conversation-review-sets.md).

       - **Datos adjuntos en la** nube: seleccione esta opción para incluir datos adjuntos modernos o archivos vinculados cuando los resultados de la colección se agregan al conjunto de revisión. Esto significa que el archivo de destino de un archivo adjunto o vinculado moderno se agrega al conjunto de revisión.

       - **Versiones de SharePoint:** seleccione esta opción para habilitar la colección de todas las versiones de un documento de SharePoint según los límites de versión y los parámetros de búsqueda de la colección. Si selecciona esta opción, aumentará significativamente el tamaño de los elementos que se agregan al conjunto de revisión.

   4. Configure las opciones para definir la escala de la colección que se agregará al conjunto de revisión:

      - **Agregar todos los resultados de la** colección: seleccione esta opción para agregar todos los elementos que coincidan con los criterios de búsqueda de la colección al conjunto de revisión.

      - **Agregar una muestra de los resultados** de la colección: seleccione esta opción para agregar una muestra de los resultados de la colección al conjunto de revisión en lugar de agregar todos los resultados. Si selecciona esta opción, haga clic **en Editar parámetros de ejemplo** y elija una de las siguientes opciones:

         - **Ejemplo basado en la confianza:** los elementos de la colección se agregan al conjunto de revisión se determinarán por los parámetros estadísticos que establezca. Si normalmente usa un nivel de confianza y un intervalo al muestrear los resultados, es preciso especificarlos en los cuadros desplegables. De lo contrario, use la configuración predeterminada.

         - **Ejemplo aleatorio:** los elementos de la colección se agregan al conjunto de revisión en función de una selección aleatoria del porcentaje especificado del número total de elementos devueltos por la búsqueda.

6. En la **página Revisar la colección,** puede revisar la configuración de la colección que configuró en la página anterior. Haga **clic en** Editar si desea cambiarlos.

7. Haga **clic en Enviar** para crear la colección borrador. Se muestra una página que confirma que se creó la colección.

## <a name="what-happens-after-you-commit-a-draft-collection"></a>Qué sucede después de confirmar un borrador de colección

Cuando se confirma un borrador de colección en un conjunto de revisión, sucede lo siguiente:

- La consulta de búsqueda de colección se vuelve a ejecutar. Esto significa que los resultados de búsqueda reales copiados en el conjunto de revisión pueden ser diferentes de los resultados estimados que se devolvieron cuando se presentó la última ejecución de la búsqueda de colección.

- Todos los elementos de los resultados de la búsqueda se copian del origen de datos original en el servicio en directo y se copian en una ubicación segura de Azure Storage en la nube de Microsoft.

- Todos los elementos (incluidos el contenido y los metadatos) que no se encuentran en orígenes de datos custodios o no custodios se reindexa (en un proceso denominado indización *profunda)* para que todos los datos del conjunto de revisión puedan buscarse completamente durante la revisión de los datos del caso. La reindexación del contenido de una colección da como resultado búsquedas exhaustivas y rápidas al buscar o filtrar el contenido del conjunto de revisión durante la investigación de casos.

- Los documentos cifrados de SharePoint y OneDrive y los mensajes de correo electrónico adjuntos a archivos cifrados que se devuelven en los resultados de búsqueda se descifran al confirmar la colección en un conjunto de revisión. Puede revisar y consultar los archivos descifrados en el conjunto de revisión. Para obtener más información, vea [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).

- La funcionalidad de reconocimiento óptico de caracteres (OCR) extrae texto de imágenes e incluye el texto de la imagen con el contenido que se agrega a un conjunto de opiniones. Para obtener más información, consulte la [sección Reconocimiento óptico de caracteres](#optical-character-recognition) de este artículo.

- Una vez completada correctamente la confirmación, el valor de la columna de estado de en la **ficha Colecciones** se cambia a `Committed` .

## <a name="optical-character-recognition"></a>Reconocimiento óptico de caracteres

Cuando se confirma una colección en un conjunto de revisión, la funcionalidad de reconocimiento óptico de caracteres (OCR) en eDiscovery avanzada extrae automáticamente texto de imágenes e incluye el texto de la imagen con el contenido que se agrega a un conjunto de opiniones. Puede ver el texto extraído en el visor de texto del archivo de imagen seleccionado en el conjunto de revisión. Esto te permite realizar más análisis y revisión del texto de las imágenes. Ocr es compatible con archivos sueltos, datos adjuntos de correo electrónico e imágenes incrustadas. Para obtener una lista de los formatos de archivo de imagen compatibles con OCR, vea [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).

Debe habilitar la funcionalidad OCR para cada caso que cree en eDiscovery avanzada. Para obtener más información, vea [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).
