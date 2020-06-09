---
title: Negoziazione di sicurezza e timeout
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: 1b5fb15b4ea00ba33b741c96bcb423aefe9890fa
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600997"
---
# <a name="security-negotiation-and-timeouts"></a>Negoziazione di sicurezza e timeout
Quando si esegue l'autenticazione di client e servizi, Windows Communication Foundation (WCF) supporta una modalità in cui la credenziale del servizio viene negoziata come parte dell'autenticazione. In scenari di questo tipo, può verificarsi uno scambio di autenticazione multifase tra il client e il servizio al fine di propagare la credenziale del servizio al client. La proprietà <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> controlla il tempo di completamento richiesto per tale scambio multifase. Questo timeout viene tuttavia applicato solo se lo scambio impiega effettivamente più tempo di una singola richiesta-risposta. Nel caso in cui la negoziazione venga completata in un singolo round trip, il timeout non viene applicato.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [Procedura: impostare lo sfasamento massimo dei segnali di clock](how-to-set-a-max-clock-skew.md)
