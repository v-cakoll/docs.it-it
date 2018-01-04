---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ed8a5718bb4a3a070f39a0dca35e2fdbc78f1b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a>System.ServiceModel.Channels.PeerMaintainerActivity
Il modulo PeerMaintainer sta eseguendo un'operazione specifica (i dettagli sono contenuti nel corpo del messaggio di traccia).  
  
## <a name="description"></a>Descrizione  
 Questa traccia si verifica durante varie operazioni PeerMaintainer.  
  
 PeerMaintainer è un componente interno di PeerNode. Ogni minuto o ogni 32 messaggi ricevuti, invia un messaggio LinkUtility ai router adiacenti con le statistiche sulla quantità di messaggi scambiati e su quanti di essi sono utili (non duplicati, non manomessi). Ciò consente di determinare l'utilità di collegamento di un determinato router adiacente. Ogni cinque minuti circa, il componente Maintener verifica l'integrità delle connessioni al router adiacente. Se il numero di connessioni al router adiacente supera il valore ideale, il componente elimina le connessioni meno utili. Se il numero di connessioni non è sufficiente, il componente ne acquisisce di nuove.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
