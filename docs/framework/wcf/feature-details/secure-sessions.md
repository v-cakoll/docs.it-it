---
title: Sessioni protette
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: cb02adc7514e27175088e7664b12e45bc8ca5cd9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590085"
---
# <a name="secure-sessions"></a>Sessioni protette
Una funzionalità di Windows Communication Foundation (WCF) è costituita da sessioni affidabili che garantiscono la ricezione di messaggi nell'ordine in cui sono stati inviati. Negli argomenti di questa sezione vengono descritte le implicazioni di sicurezza da tenere presenti quando si crea una sessione affidabile. Per ulteriori informazioni sulle sessioni affidabili, vedere [Using Sessions](../using-sessions.md).  
  
> [!NOTE]
> Quando la rappresentazione è obbligatoria in Windows XP, utilizzare una sessione protetta priva di token del contesto di sicurezza (SCT, Security Context Token) con stato. Infatti, quando i token SCT con stato vengono utilizzati con la rappresentazione, il sistema genera un'eccezione <xref:System.InvalidOperationException>. Per altre informazioni, vedere [scenari non supportati](unsupported-scenarios.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
  
|||  
|-|-|  
|[Conversazioni e sessioni protette](secure-conversations-and-secure-sessions.md)|Il termine "conversazione protetta" è sinonimo di "sessione protetta". In questo argomento viene illustrato il funzionamento di una conversazione protetta nonché i contesti in cui utilizzare tale modello.|  
|[Procedura: creare una sessione protetta](how-to-create-a-secure-session.md)|Questo argomento descrive i passaggi della procedura di base per creare una sessione protetta.|  
|[Procedura: creare un token di contesto di sicurezza per una sessione sicura](how-to-create-a-security-context-token-for-a-secure-session.md)|Questo argomento descrive i passaggi della procedura per creare una Web farm che interagisce con i client tramite una sessione protetta con stato.|  
|[Considerazioni sulla protezione per le sessioni protette](security-considerations-for-secure-sessions.md)|Questo argomento contiene considerazioni specifiche sulle sessioni protette.|  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Sessioni, istanze e concorrenza](sessions-instancing-and-concurrency.md)  
  
 [Progettazione e implementazione di servizi](../designing-and-implementing-services.md)  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: attivare il rilevamento di attacchi di tipo replay dei messaggi](how-to-enable-message-replay-detection.md)
- [Attacchi di tipo replay](replay-attacks.md)
- [Procedura: creare un servizio che richiede sessioni](how-to-create-a-service-that-requires-sessions.md)
