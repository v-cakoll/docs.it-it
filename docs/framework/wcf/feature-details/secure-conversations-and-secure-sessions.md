---
title: Conversazioni e sessioni protette
ms.date: 03/30/2017
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
ms.openlocfilehash: 887b2e6e6553a910de046950514869907519cf35
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746457"
---
# <a name="secure-conversations-and-secure-sessions"></a>Conversazioni e sessioni protette
Una funzionalità di Windows Communication Foundation (WCF) è la possibilità di stabilire sessioni sicure tra due endpoint che si autenticano reciprocamente e concordano su un processo di crittografia e firma digitale. L'endpoint del servizio potrebbe, ad esempio, richiedere a un endpoint client di inviare un token di sicurezza basato su un certificato X.509 per l'autenticazione. Dopo che il client è stato autenticato, l'endpoint del servizio restituisce un token del contesto di sicurezza (SCT) al client che viene quindi utilizzato per proteggere tutti i messaggi successivi all'interno della sessione. La creazione di questa sessione protetta consente al set di messaggi scambiati tra due endpoint di essere più efficienti, poiché SCT ha una chiave simmetrica. Le chiavi asimmetriche, sulle quali sono basati i certificati X.509, richiedono una potenza di calcolo notevolmente maggiore rispetto alle chiavi simmetriche per generare una firma digitale o la crittografia di un set di dati.  
  
 Il criterio bootstrap (definito nella sezione 6.2.7 dello standard [WS-SecurityPolicy](https://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/ws-securitypolicy-1.2-spec-os.html) ) contiene le asserzioni di sicurezza dei messaggi utilizzate per proteggere il canale e autenticare il client prima dello scambio RST/SCT e RSTR/SCT. Alcune associazioni standard WCF hanno una proprietà `Security.Message.EstablishSecurityContext` che controlla se viene utilizzata la conversazione protetta. Quando si usano associazioni personalizzate, il bootstrap è indicato annidando gli elementi di associazione di sicurezza, tramite [\<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) nel file di configurazione o chiamando <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> nel codice.  
  
 Per ulteriori informazioni sulle sessioni, vedere [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).  
  
## <a name="see-also"></a>Vedere anche

- [Sessioni, istanze e concorrenza](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
- [Procedura: Creare un servizio che richiede sessioni](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
