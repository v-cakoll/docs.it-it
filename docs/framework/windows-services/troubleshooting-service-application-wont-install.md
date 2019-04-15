---
title: "Risoluzione dei problemi: Impossibile installare l'applicazione di servizio"
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
author: ghogen
ms.openlocfilehash: f75a2f33ecde408d2d8e2f2343197ba56c4b8c21
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143819"
---
# <a name="troubleshooting-service-application-wont-install"></a>Risoluzione dei problemi: Impossibile installare l'applicazione di servizio
Se l'applicazione di servizio non viene installata correttamente, verificare che la proprietà <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> per la classe del servizio sia impostata sullo stesso valore indicato nel programma di installazione per il servizio. Il valore deve essere uguale in entrambe le istanze per ottenere la corretta installazione del servizio.  
  
> [!NOTE]
>  È anche possibile esaminare i log di installazione per ottenere informazioni sul processo di installazione.  
  
 Controllare inoltre se esiste un altro servizio con lo stesso nome già installato. I nomi di servizio devono essere univoci per l'esito positivo dell'installazione.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
