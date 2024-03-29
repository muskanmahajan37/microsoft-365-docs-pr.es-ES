---
title: Agregar preguntas personalizadas y requeridas a la página de reserva
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: fd6b7587-5055-4bcd-83a4-13bd4929bfff
description: Si necesita hacer preguntas a los clientes cuando reserven una cita con usted en línea, puede agregar preguntas personalizadas y obligatorias a la página de reserva.
ms.openlocfilehash: ebbb07857fd8bb196f769dfb7e71ad25a85dfd54
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420179"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a>Agregar preguntas personalizadas y requeridas a la página de reserva

Bookings le permite crear preguntas para hacer preguntas a los clientes cuando reservan citas. También le permite elegir qué preguntas son necesarias.

Las preguntas se asocian a un servicio, por lo que cada servicio puede tener un conjunto de preguntas diferente. Por ejemplo, un diseñador de vellos puede preguntar a los clientes que están reservando una cita para colorear el vello si tienen alguna idea conocida de infilaciones o tono. Esto te permite a ti y a tus clientes ahorrar tiempo cuando lleguen a su cita.

Los clientes verán las preguntas personalizadas cuando creen su cita en la página de reserva. El personal verá las preguntas personalizadas al crear una nueva reserva desde el calendario de Bookings o al ver una cita existente. Bookings guarda todas las preguntas en una lista maestra para que no tenga que volver a crear las mismas preguntas para cada servicio. También puede elegir si las preguntas son obligatorias u opcionales.

> [!NOTE]
> Las respuestas del cliente a las preguntas se pueden ver al mirar su cita en el calendario de reserva.

Para obtener más información acerca de cómo personalizar y personalizar la página de reserva, vea [Personalizar la página de reserva.](customize-booking-page.md)

## <a name="add-custom-questions-to-your-services"></a>Agregar preguntas personalizadas a los servicios

1. Inicie sesión en Microsoft 365 y vaya a **Bookings**.

1. Vaya a **Servicios** y edite un servicio existente o **agregue un servicio.**

1. Desplácese hacia abajo hasta la **sección Campos personalizados** y, a continuación, **seleccione Modificar**.

   Ya hemos agregado algunas preguntas básicas sobre la información del cliente: correo electrónico del cliente, número de teléfono, dirección del cliente y notas del cliente. La primera vez que lo hagas, las preguntas de información del cliente se resaltan en gris. Esto significa que el usuario verá esta pregunta. Si seleccionas la pregunta, el cuadro de resaltado que lo rodea desaparecerá y no se hará esa pregunta al cliente.

   En este ejemplo, se han desactivado el número de teléfono y las notas del cliente y hemos creado dos nuevas preguntas personalizadas para hacer.

   ![Imagen de la pantalla de preguntas personalizadas](../media/bookings-questions-custom-fields.png)

1. Para que la pregunta sea obligatoria, active la **casilla Obligatorio.** El cliente no podrá completar la reserva hasta que haya respondido a las preguntas necesarias.

1. Para crear una pregunta personalizada, seleccione **Agregar una** pregunta en la parte superior del panel. Escriba su pregunta y, a continuación, **seleccione Guardar**.

1. Haga clic en la pregunta para habilitarla. Aparece un cuadro resaltado a su alrededor y la pregunta está habilitada.

1. Haga **clic en** Aceptar en la parte superior de la página y, a continuación, guarde el **servicio.**

Bookings guardará todas las preguntas personalizadas en una lista maestra para que pueda agregar fácilmente preguntas a cada servicio sin necesidad de escribir repetidamente las mismas preguntas. Por ejemplo, si abre un servicio diferente, la pregunta que creó para el primer servicio se mostrará en la sección Campos personalizados, pero se deshabilitará. Haga clic en la pregunta para que se muestre un rectángulo resaltado y la pregunta esté habilitada.

En este ejemplo, puede ver que las preguntas que se agregaron para el primer servicio están disponibles para este servicio. Las preguntas que cree para este servicio estarán disponibles para todos los servicios.

   ![Imagen de preguntas que aparecen para varios servicios](../media/bookings-questions-services.png)

Si la página de reserva ya está publicada, no es necesario hacer nada más. Los clientes verán las preguntas la próxima vez que se reserven contigo. Si la página de reserva aún no  está publicada, vaya a la página de reserva desde Outlook en la Web y, a continuación, seleccione **Guardar y publicar.**

> [!WARNING]
> También puede eliminar preguntas de la lista maestra. Sin embargo, si elimina una pregunta, se eliminará de todos los servicios. Le recomendamos que deshabilite la pregunta seleccionándosela para asegurarse de que no afecta a ningún otro servicio. Puedes ver que una pregunta está deshabilitada si no está rodeada por un rectángulo resaltado.

## <a name="customer-experience"></a>Experiencia del cliente

Cuando tus clientes reserven una cita contigo, las preguntas básicas sobre la información del cliente se mostrarán en la **sección Agregar detalles.** Las preguntas personalizadas que agregue estarán en la **sección Proporcionar información** adicional.

![Imagen de lo que ven los clientes cuando se habilitan las preguntas](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a>Experiencia del personal

Cuando tus clientes reserven una cita contigo, el personal verá las preguntas y las respuestas del cliente en el calendario de reserva. Para verlo, vaya a Calendario **de Bookings** \> **y,** a continuación, abra una cita.

![Imagen de lo que ve el personal cuando se habilitan las preguntas](../media/bookings-questions-staff.png)
