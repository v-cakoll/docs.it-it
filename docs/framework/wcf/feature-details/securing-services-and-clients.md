---
title: Protezione di servizi e client
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 60aa4da95666de01daa087c4c8e826c8cf72ba85
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "46003074"
---
# <a name="securing-services-and-clients"></a>Protezione di servizi e client
Le informazioni contenute in questa sezione è incentrata sulla programmazione della protezione in Windows Communication Foundation (WCF). Quest'attività include, in genere, la selezione di un'associazione fornita dal sistema appropriata, l'impostazione delle proprietà dell'elemento di sicurezza e quindi l'impostazione delle proprietà dei comportamenti del servizio che regolano la modalità di recupero delle credenziali che devono essere usate dal servizio o dal client. Queste tecniche soddisfano i requisiti di sicurezza della maggior parte degli utenti per la maggior parte degli scenari, come illustrato nella [scenari di sicurezza comuni](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md). Se lo scenario richiede altre funzionalità, vedere innanzitutto [funzionalità di sicurezza con associazioni personalizzate](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); se una soluzione non è evidente, vedere [estensione di sicurezza](../../../../docs/framework/wcf/extending/extending-security.md). Se si sta creando (o interagisce con) un sistema che usa attestazioni dettagliate, vedere gli argomenti in [autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Programmazione delle funzionalità di sicurezza di WCF](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 Panoramica del modello di programmazione usato per proteggere i messaggi.  
  
 [Panoramica della sicurezza del trasporto](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 Panoramica delle modalità di sicurezza dei messaggi tramite il livello di trasporto.  
  
 [Sicurezza dei messaggi](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 Riepilogo dei motivi per l'uso di sicurezza a livello di messaggio in Windows Communication Foundation (WCF).  
  
 [Sessioni sicure](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 Una descrizione delle considerazioni necessarie per la protezione di una sessione WCF.  
  
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
 [Modello di sicurezza per Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
