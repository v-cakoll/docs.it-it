---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 6fb1463b811d985f54b9a99e59d1280eaa040256
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="systemservicemodelmessageprocessingpaused"></a>System.ServiceModel.MessageProcessingPaused
System.ServiceModel.MessageProcessingPaused  
  
## <a name="description"></a>Descrizione  
 I thread sono stati commutati durante l'elaborazione di un messaggio.  
  
 L'elaborazione messaggi può essere interrotta per le ragioni seguenti:  
  
-   ConcurrencyMode è singolo o rientrante e il servizio sta elaborando un altro messaggio.  
  
-   La transazione è attivata e il servizio sta elaborando un'altra transazione.  
  
-   Il contesto di sincronizzazione non è aggiornato.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
