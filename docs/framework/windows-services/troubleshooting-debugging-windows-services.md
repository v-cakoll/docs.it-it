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
manager: douge
ms.openlocfilehash: 77a0c19c2da2d1886beaf396650fa024fc1243a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-debugging-windows-services"></a>Risoluzione dei problemi: debug dei servizi Windows
Quando si esegue il debug di un'applicazione di servizio Windows, il servizio e **Windows Service Manager** interagire. Il **Service Manager** avvia il servizio chiamando il <xref:System.ServiceProcess.ServiceBase.OnStart%2A> (metodo), quindi attende 30 secondi per il <xref:System.ServiceProcess.ServiceBase.OnStart%2A> restituzione del metodo. Se il metodo non restituisce in questo periodo, il gestore viene visualizzato un errore che può essere avviato il servizio.  
  
 Quando esegue il debug la <xref:System.ServiceProcess.ServiceBase.OnStart%2A> (metodo), come descritto in [procedura: eseguire il Debug di applicazioni di servizio Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), è necessario essere a conoscenza di questo periodo di 30 secondi. Se si inserisce un punto di interruzione di <xref:System.ServiceProcess.ServiceBase.OnStart%2A> metodo e non eseguire un'istruzione entro 30 secondi, il gestore non avvierà il servizio.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: eseguire il debug di applicazioni di servizio per Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
