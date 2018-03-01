---
title: Protezione di servizi e client
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 52e07a83f5a1b84abc46f00e6fd6e80e4b9a2622
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="securing-services-and-clients"></a>Protezione di servizi e client
Le informazioni in questa sezione si concentrano sulla programmazione della protezione in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Quest'attività include, in genere, la selezione di un'associazione fornita dal sistema appropriata, l'impostazione delle proprietà dell'elemento di sicurezza e quindi l'impostazione delle proprietà dei comportamenti del servizio che regolano la modalità di recupero delle credenziali che devono essere usate dal servizio o dal client. Queste tecniche di soddisfare i requisiti di sicurezza della maggior parte degli utenti per la maggior parte degli scenari, come illustrato nel [comuni scenari di sicurezza](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md). Se lo scenario richiede altre funzionalità, vedere prima [funzionalità di sicurezza con associazioni personalizzate](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); se una soluzione non è evidente, vedere [estensione sicurezza](../../../../docs/framework/wcf/extending/extending-security.md). Se Crea (o si interagisce con) un sistema che utilizza le attestazioni avanzate, vedere gli argomenti in [autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Programmazione delle funzionalità di sicurezza di WCF](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 Panoramica del modello di programmazione usato per proteggere i messaggi.  
  
 [Panoramica della sicurezza del trasporto](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 Panoramica delle modalità di sicurezza dei messaggi tramite il livello di trasporto.  
  
 [Sicurezza dei messaggi](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 Riepilogo dei motivi per l'uso della protezione a livello di messaggio in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
 [Sessioni sicure](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 Descrizione delle considerazioni necessarie in caso di sicurezza di una sessione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Uso di certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 Spiegazione di alcune delle attività comuni necessarie quando si usano certificati X.509.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Concetti relativi alla sicurezza](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [Estensione della sicurezza](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [Scenari di sicurezza comuni](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [Associazioni e sicurezza](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [Funzionalità di sicurezza con associazioni personalizzate](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [Estensione della sicurezza](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [Autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Programmazione WCF di base](../../../../docs/framework/wcf/basic-wcf-programming.md)  
 [Modello di sicurezza per Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
