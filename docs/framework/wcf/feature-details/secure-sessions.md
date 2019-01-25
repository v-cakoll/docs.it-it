---
title: Sessioni protette
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: 63e363e90a656c918b68d3f86d8b6ad3b7a540e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715712"
---
# <a name="secure-sessions"></a>Sessioni protette
Le sessioni affidabili che garantiscono che i messaggi vengono ricevuti nell'ordine in che cui sono stati inviati è una funzionalità di Windows Communication Foundation (WCF). Negli argomenti di questa sezione vengono descritte le implicazioni di sicurezza da tenere presenti quando si crea una sessione affidabile. Per altre informazioni sulle sessioni affidabili, vedere [utilizzando le sessioni](../../../../docs/framework/wcf/using-sessions.md).  
  
> [!NOTE]
>  Quando la rappresentazione è obbligatoria in Windows XP, utilizzare una sessione protetta priva di token del contesto di sicurezza (SCT, Security Context Token) con stato. Infatti, quando i token SCT con stato vengono utilizzati con la rappresentazione, il sistema genera un'eccezione <xref:System.InvalidOperationException>. Per altre informazioni, vedere [scenari non supportati](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
## <a name="in-this-section"></a>In questa sezione  
  
|||  
|-|-|  
|[Conversazioni e sessioni sicure](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|Il termine "conversazione protetta" è sinonimo di "sessione protetta". In questo argomento viene illustrato il funzionamento di una conversazione protetta nonché i contesti in cui usare tale modello.|  
|[Procedura: Creare una sessione protetta](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|Questo argomento descrive i passaggi della procedura di base per creare una sessione protetta.|  
|[Procedura: Creare un contesto di sicurezza Token per una sessione protetta](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|Questo argomento descrive i passaggi della procedura per creare una Web farm che interagisce con i client tramite una sessione protetta con stato.|  
|[Considerazioni sulla sicurezza per le sessioni sicure](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|Questo argomento contiene considerazioni specifiche sulle sessioni protette.|  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Sessioni, istanze e concorrenza](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [Progettazione e implementazione di servizi](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Abilitare il rilevamento riproduzione messaggio](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)
- [Attacchi di tipo replay](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
- [Procedura: Creare un servizio che richiede sessioni](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
