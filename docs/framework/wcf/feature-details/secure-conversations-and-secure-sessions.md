---
title: Conversazioni e sessioni protette
ms.date: 03/30/2017
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
author: BrucePerlerMS
ms.openlocfilehash: 077f21f11fae9e91abe281778351954c80d9603b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47199801"
---
# <a name="secure-conversations-and-secure-sessions"></a>Conversazioni e sessioni protette
Una funzionalità di Windows Communication Foundation (WCF) è la possibilità di stabilire sessioni protette tra due endpoint che si autenticano a vicenda e si accordano su un processo di crittografia e firma digitale. L'endpoint del servizio potrebbe, ad esempio, richiedere a un endpoint client di inviare un token di sicurezza basato su un certificato X.509 per l'autenticazione. Dopo che il client è stato autenticato, l'endpoint del servizio restituisce un token del contesto di sicurezza (SCT) al client che viene quindi utilizzato per proteggere tutti i messaggi successivi all'interno della sessione. La creazione di questa sessione protetta consente al set di messaggi scambiati tra due endpoint di essere più efficienti, poiché SCT ha una chiave simmetrica. Le chiavi asimmetriche, sulle quali sono basati i certificati X.509, richiedono una potenza di calcolo notevolmente maggiore rispetto alle chiavi simmetriche per generare una firma digitale o la crittografia di un set di dati.  
  
 Il criterio bootstrap (definito nella sezione 6.2.7 il [WS-SecurityPolicy](https://go.microsoft.com/fwlink/?LinkId=99817) standard) contiene le asserzioni di sicurezza messaggio utilizzate per proteggere il canale e autenticare il client prima dello scambio RST/SCT e RSTR/SCT. Alcune associazioni di WCF standard hanno un `Security.Message.EstablishSecurityContext` proprietà che controlla se secure conversation viene utilizzata. Quando si utilizzano associazioni personalizzate il bootstrap viene indicato da nidificazione elementi di associazione della protezione, tramite [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) nel file di configurazione o chiamando <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> nel codice.  
  
 Per altre informazioni sulle sessioni, vedere [utilizzando le sessioni](../../../../docs/framework/wcf/using-sessions.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Sessioni, istanze e concorrenza](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [Procedura: Creare un servizio che richiede sessioni](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
