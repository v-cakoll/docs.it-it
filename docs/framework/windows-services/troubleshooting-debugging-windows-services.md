---
title: 'Risoluzione dei problemi: debug dei servizi Windows'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 51c28f6e9b6fa2974fb9861716b2c9fc2a38fe1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-debugging-windows-services"></a>Risoluzione dei problemi: debug dei servizi Windows
Quando si esegue il debug di un'applicazione di servizio Windows, il servizio e **Windows Service Manager** interagire. Il **Service Manager** avvia il servizio chiamando il <xref:System.ServiceProcess.ServiceBase.OnStart%2A> (metodo), quindi attende 30 secondi per il <xref:System.ServiceProcess.ServiceBase.OnStart%2A> restituzione del metodo. Se il metodo non restituisce in questo periodo, il gestore viene visualizzato un errore che può essere avviato il servizio.  
  
 Quando esegue il debug la <xref:System.ServiceProcess.ServiceBase.OnStart%2A> (metodo), come descritto in [procedura: eseguire il Debug di applicazioni di servizio Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), è necessario essere a conoscenza di questo periodo di 30 secondi. Se si inserisce un punto di interruzione di <xref:System.ServiceProcess.ServiceBase.OnStart%2A> metodo e non eseguire un'istruzione entro 30 secondi, il gestore non avvierà il servizio.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: eseguire il Debug di applicazioni di servizio Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
