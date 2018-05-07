---
title: 'Risoluzione dei problemi: Opportunità vinte applicazione del servizio&#39;Install t'
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
manager: douge
ms.openlocfilehash: 1f3e5674f9a52627efdc24d6c70c0ab16dcdbbbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-service-application-won39t-install"></a>Risoluzione dei problemi: Opportunità vinte applicazione del servizio&#39;Install t
Se l'applicazione di servizio non verrà installato correttamente, verificare che il <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> proprietà per la classe del servizio è impostata sullo stesso valore, come illustrato nel programma di installazione per il servizio. Il valore deve essere la stessa in entrambe le istanze del servizio installare correttamente.  
  
> [!NOTE]
>  È anche possibile esaminare i registri di installazione per ottenere informazioni sul processo di installazione.  
  
 Controllare inoltre per determinare se si dispone di un altro servizio con lo stesso nome già installato. I nomi di servizio devono essere univoci per l'installazione abbia esito positivo.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
