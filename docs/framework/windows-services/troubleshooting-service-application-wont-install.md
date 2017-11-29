---
title: "Risoluzione dei problemi: Opportunità vinte applicazione di servizio &#39; installare t"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 82eb870761a7865385631cd9961ce99e0b0d3502
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="troubleshooting-service-application-won39t-install"></a>Risoluzione dei problemi: Opportunità vinte applicazione di servizio &#39; installare t
Se l'applicazione di servizio non verrà installato correttamente, verificare che il <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> proprietà per la classe del servizio è impostata sullo stesso valore, come illustrato nel programma di installazione per il servizio. Il valore deve essere la stessa in entrambe le istanze del servizio installare correttamente.  
  
> [!NOTE]
>  È anche possibile esaminare i registri di installazione per ottenere informazioni sul processo di installazione.  
  
 Controllare inoltre per determinare se si dispone di un altro servizio con lo stesso nome già installato. I nomi di servizio devono essere univoci per l'installazione abbia esito positivo.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
