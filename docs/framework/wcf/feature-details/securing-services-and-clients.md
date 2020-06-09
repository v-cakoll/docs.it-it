---
title: Protezione di servizi e client
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: db0a0dcfbe04a7b7dbfabfed59f9b8637d0a2797
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84586208"
---
# <a name="securing-services-and-clients"></a>Protezione di servizi e client
Le informazioni contenute in questa sezione sono incentrate sulla sicurezza della programmazione in Windows Communication Foundation (WCF). Quest'attività include, in genere, la selezione di un'associazione fornita dal sistema appropriata, l'impostazione delle proprietà dell'elemento di sicurezza e quindi l'impostazione delle proprietà dei comportamenti del servizio che regolano la modalità di recupero delle credenziali che devono essere usate dal servizio o dal client. Queste tecniche coprono i requisiti di sicurezza della maggior parte degli utenti per la maggior parte degli scenari, come illustrato negli [scenari di sicurezza comuni](common-security-scenarios.md). Se lo scenario richiede più funzionalità, vedere innanzitutto [funzionalità di sicurezza con associazioni personalizzate](security-capabilities-with-custom-bindings.md). Se una soluzione non è evidente, vedere [estensione della sicurezza](../extending/extending-security.md). Se si crea o si interopera con un sistema che utilizza attestazioni avanzate, vedere gli argomenti in [autorizzazione](authorization-in-wcf.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Programmazione delle funzionalità di sicurezza di WCF](programming-wcf-security.md)  
 Panoramica del modello di programmazione usato per proteggere i messaggi.  
  
 [Panoramica sulla sicurezza del trasporto](transport-security-overview.md)  
 Panoramica delle modalità di sicurezza dei messaggi tramite il livello di trasporto.  
  
 [Sicurezza dei messaggi](message-security-in-wcf.md)  
 Riepiloga i motivi per l'utilizzo della sicurezza a livello di messaggio nel Windows Communication Foundation (WCF).  
  
 [Sessioni protette](secure-sessions.md)  
 Descrizione delle considerazioni necessarie per la protezione di una sessione WCF.  
  
 [Working with Certificates](working-with-certificates.md)  
 Spiegazione di alcune delle attività comuni necessarie quando si usano certificati X.509.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Concetti relativi alla sicurezza](security-concepts.md)  
  
 [Estensione della protezione](../extending/extending-security.md)  
  
 [Scenari di sicurezza comuni](common-security-scenarios.md)  
  
 [Associazioni e protezione](bindings-and-security.md)  
  
 [Funzionalità di sicurezza con associazioni personalizzate](security-capabilities-with-custom-bindings.md)  
  
 [Estensione della protezione](../extending/extending-security.md)  
  
 [Autorizzazione](authorization-in-wcf.md)  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione WCF di base](../basic-wcf-programming.md)
- [Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
