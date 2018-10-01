---
title: 'Risoluzione dei problemi: debug dei servizi Windows'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- troubleshooting service applications
- services, troubleshooting
- troubleshooting debugging, Windows Services
- Windows Service applications, debugging
- services, debugging
- Windows Service applications, troubleshooting
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
author: ghogen
ms.openlocfilehash: 0dbbebd14ce0ff5f69a12c256238c7e0a02494cb
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47199944"
---
# <a name="troubleshooting-debugging-windows-services"></a>Risoluzione dei problemi: debug dei servizi Windows
Quando si esegue il debug di un'applicazione di servizio Windows, il servizio e **Windows Service Manager** interagiscono. **Service Manager** avvia il servizio chiamando il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, quindi attende 30 secondi che il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> restituisca il controllo. Se il metodo non restituisce il controllo entro questo periodo, il gestore visualizza un errore per indicare che non è possibile avviare il servizio.  
  
 Quando si esegue il debug del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, come descritto in [Procedura: Eseguire il debug di applicazioni di servizio per Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), è necessario essere a conoscenza di questo periodo di 30 secondi. Se si inserisce un punto di interruzione nel metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e non si procede entro 30 secondi, il gestore non avvierà il servizio.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: eseguire il debug di applicazioni di servizio per Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
