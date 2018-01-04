---
title: Conversazioni e sessioni protette
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: d519640c40daf248a01a19f0450f3aea8de6cc04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="secure-conversations-and-secure-sessions"></a>Conversazioni e sessioni protette
Una funzionalità di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] è la possibilità di stabilire sessioni protette tra due endpoint che si autenticano a vicenda e si accordano su un processo di crittografia e di firma digitale. L'endpoint del servizio potrebbe, ad esempio, richiedere a un endpoint client di inviare un token di sicurezza basato su un certificato X.509 per l'autenticazione. Dopo che il client è stato autenticato, l'endpoint del servizio restituisce un token del contesto di sicurezza (SCT) al client che viene quindi utilizzato per proteggere tutti i messaggi successivi all'interno della sessione. La creazione di questa sessione protetta consente al set di messaggi scambiati tra due endpoint di essere più efficienti, poiché SCT ha una chiave simmetrica. Le chiavi asimmetriche, sulle quali sono basati i certificati X.509, richiedono una potenza di calcolo notevolmente maggiore rispetto alle chiavi simmetriche per generare una firma digitale o la crittografia di un set di dati.  
  
 I criteri di bootstrap (definiti nella sezione 6.2.7 del [WS-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817) standard) contiene le asserzioni di sicurezza messaggio utilizzate per proteggere il canale e autenticare il client prima dello scambio RST/SCT e RSTR/SCT. Alcune associazioni standard di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dispongono di una proprietà `Security.Message.EstablishSecurityContext` che controlla l'utilizzo delle conversazioni protette. Quando si utilizzano associazioni personalizzate il programma di avvio è indicato dall'annidamento elementi di associazione di sicurezza, tramite [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) nel file di configurazione o chiamando <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> nel codice.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]le sessioni, vedere [utilizzando le sessioni](../../../../docs/framework/wcf/using-sessions.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Sessioni, istanze e concorrenza](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [Procedura: Creare un servizio che richiede sessioni](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
