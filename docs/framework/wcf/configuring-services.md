---
title: Configurazione dei servizi
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: 1246ce5056c17641e10bb96f79b60090d6f43b89
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525053"
---
# <a name="configuring-services"></a>Configurazione dei servizi
Dopo aver progettato e implementato il contratto di servizio, è possibile configurare il servizio. Questa è la fase in cui si definisce e si personalizza il modo in cui il servizio viene esposto ai client, inclusa l'indicazione dell'indirizzo, del trasporto e della codifica dei messaggi usata per inviare e ricevere messaggi e del tipo di sicurezza richiesto.  
  
 La configurazione specificata in questo punto include tutti i modi, imperativo nel codice o mediante un file di configurazione, in cui è possibile definire e personalizzare i vari aspetti di un servizio, ad esempio la specifica degli indirizzi dell'endpoint, dei trasporti usati e degli schemi di sicurezza. In pratica, la creazione della configurazione è un'importante parte della programmazione di applicazioni WCF.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Configurazione semplificata](../../../docs/framework/wcf/simplified-configuration.md)  
 A partire da [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF viene fornito con un nuovo modello di configurazione predefinito che semplifica i requisiti di configurazione WCF. Se non si specifica alcuna configurazione di WCF per un determinato servizio, il runtime configura automaticamente il servizio con i comportamenti, associazioni e gli endpoint predefiniti.  
  
 [Configurazione dei servizi tramite file di configurazione](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 È un servizio di Windows Communication Foundation (WCF) può essere configurato utilizzando il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] la tecnologia di configurazione. In genere, gli elementi XML vengono aggiunti al file Web. config per un sito Internet Information Services (IIS) che ospita un servizio WCF. Gli elementi consentono di modificare i dettagli, ad esempio gli indirizzi dell'endpoint (gli indirizzi effettivi usati per comunicare con il servizio) per i singoli computer.  
  
 [Associazioni](../../../docs/framework/wcf/bindings.md)  
 Inoltre, WCF include numerose configurazioni comuni fornite dal sistema sotto forma di associazioni che consentono di selezionare rapidamente le funzionalità di base per la comunicazione tra client e servizio, ad esempio i trasporti, sicurezza e messaggio codifiche utilizzate.  
  
 [Endpoint](../../../docs/framework/wcf/endpoints.md)  
 Si verifica tutte le comunicazioni con un servizio WCF tramite il *endpoint* del servizio. Gli endpoint contengono il contratto, le informazioni di configurazione specificate nelle associazioni e gli indirizzi che indicano dove si trova il servizio o dove ottenere informazioni sul servizio.  
  
 [Protezione dei servizi](../../../docs/framework/wcf/securing-services.md)  
 Utilizzo di WCF e con meccanismi di sicurezza, è possibile implementare la riservatezza, integrità, l'autenticazione e autorizzazione in qualsiasi servizio. È inoltre possibile controllare le attività di sicurezza riuscite e non riuscite.  
  
 [Creazione di servizi interoperativi WS-I Basic Profile 1.1](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 I requisiti per la distribuzione di un servizio che sia interoperativo con i servizi e i client su qualsiasi altra piattaforma o sistema operativo sono delineati nella specifica WS-I Basic Profile 1.1.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Ciclo di vita della programmazione di base](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [Progettazione e implementazione di servizi](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [Servizi di hosting](../../../docs/framework/wcf/hosting-services.md)  
  
 [Creazione di client](../../../docs/framework/wcf/building-clients.md)  
  
 [Introduzione all'estendibilità](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [Amministrazione e diagnostica](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a>Vedere anche
- [Programmazione WCF di base](../../../docs/framework/wcf/basic-wcf-programming.md)
- [Panoramica dei concetti](../../../docs/framework/wcf/conceptual-overview.md)
- [Dettagli delle funzionalità di WCF](../../../docs/framework/wcf/feature-details/index.md)
