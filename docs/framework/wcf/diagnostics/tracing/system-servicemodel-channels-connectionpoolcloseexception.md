---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c7a134a60656c6ee237203b69e1bce40656f13d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a>System.ServiceModel.Channels.ConnectionPoolCloseException
Si è verificata un'eccezione durante la chiusura delle connessioni in questo pool di connessioni.  
  
## <a name="description"></a>Descrizione  
 Questa analisi del livello di errore indica che si è verificato un errore durante la chiusura dei pool di connessioni utilizzati dalla funzionalità di pool di connessioni di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]. Una possibile ragione è un chiusura non riuscita di una o più connessioni in pool all'interno di CloseTimeout. Quando viene generata questa eccezione, tutte le connessioni rimanenti non chiuse all'interno di tale pool vengono interrotte; le connessioni non chiuse all'interno di altri pool vengono abbandonate.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
