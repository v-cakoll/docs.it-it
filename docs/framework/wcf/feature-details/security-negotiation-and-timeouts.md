---
title: Negoziazione di sicurezza e timeout
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: dfabdb05c7658e3cf9eb5b325597360bbc0bb588
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50037798"
---
# <a name="security-negotiation-and-timeouts"></a>Negoziazione di sicurezza e timeout
Quando l'autenticazione client e servizi, Windows Communication Foundation (WCF) supporta una modalità in cui la credenziale del servizio viene negoziata nell'ambito dell'autenticazione. In scenari di questo tipo, può verificarsi uno scambio di autenticazione multifase tra il client e il servizio al fine di propagare la credenziale del servizio al client. La proprietà <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> controlla il tempo di completamento richiesto per tale scambio multifase. Questo timeout viene tuttavia applicato solo se lo scambio impiega effettivamente più tempo di una singola richiesta-risposta. Nel caso in cui la negoziazione venga completata in un singolo round trip, il timeout non viene applicato.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 [Procedura: Impostare lo sfasamento massimo dei segnali di clock](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
