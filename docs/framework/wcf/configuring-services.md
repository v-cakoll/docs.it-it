---
title: Configurazione dei servizi WCF
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: 332a88530010197187ca3ea787e152b0c95a5514
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141593"
---
# <a name="configuring-wcf-services"></a>Configurazione dei servizi WCF

Dopo aver progettato e implementato il contratto di servizio, è possibile configurare il servizio. Questa è la fase in cui si definisce e si personalizza il modo in cui il servizio viene esposto ai client, inclusa l'indicazione dell'indirizzo, del trasporto e della codifica dei messaggi usata per inviare e ricevere messaggi e del tipo di sicurezza richiesto.  
  
 La configurazione specificata in questo punto include tutti i modi, imperativo nel codice o mediante un file di configurazione, in cui è possibile definire e personalizzare i vari aspetti di un servizio, ad esempio la specifica degli indirizzi dell'endpoint, dei trasporti usati e degli schemi di sicurezza. In pratica, la scrittura della configurazione è una parte essenziale della programmazione di applicazioni WCF.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Configurazione semplificata](simplified-configuration.md)  
 A partire da .NET Framework 4, WCF viene fornita con un nuovo modello di configurazione predefinito che semplifica i requisiti di configurazione di WCF. Se non si fornisce alcuna configurazione WCF per un determinato servizio, il runtime configura automaticamente il servizio con endpoint, associazioni e comportamenti predefiniti.  
  
 [Configurazione dei servizi tramite file di configurazione](configuring-services-using-configuration-files.md)  
 Un servizio Windows Communication Foundation (WCF) è configurabile mediante la tecnologia di configurazione .NET Framework. In genere, gli elementi XML vengono aggiunti al file Web. config per un sito Internet Information Services (IIS) che ospita un servizio WCF. Gli elementi consentono di modificare i dettagli, ad esempio gli indirizzi dell'endpoint (gli indirizzi effettivi usati per comunicare con il servizio) per i singoli computer.  
  
 [Associazioni](bindings.md)  
 Inoltre, WCF include diverse configurazioni comuni fornite dal sistema sotto forma di binding che consentono di selezionare rapidamente le funzionalità di base per la comunicazione di un client e di un servizio, ad esempio i trasporti, la sicurezza e la codifica dei messaggi utilizzati.  
  
 [Endpoint](endpoints.md)  
 Tutte le comunicazioni con un servizio WCF avvengono tramite gli *endpoint* del servizio. Gli endpoint contengono il contratto, le informazioni di configurazione specificate nelle associazioni e gli indirizzi che indicano dove si trova il servizio o dove ottenere informazioni sul servizio.  
  
 [Protezione dei servizi](securing-services.md)  
 Grazie a WCF e ai meccanismi di sicurezza esistenti, è possibile implementare la riservatezza, l'integrità, l'autenticazione e l'autorizzazione in qualsiasi servizio. È inoltre possibile controllare le attività di sicurezza riuscite e non riuscite.  
  
 [Creazione di servizi interoperativi WS-I Basic Profile 1.1](./creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 I requisiti per la distribuzione di un servizio che sia interoperativo con i servizi e i client su qualsiasi altra piattaforma o sistema operativo sono delineati nella specifica WS-I Basic Profile 1.1.  
  
## <a name="reference"></a>Reference  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Ciclo di vita della programmazione di base](basic-programming-lifecycle.md)  
  
 [Progettazione e implementazione di servizi](designing-and-implementing-services.md)  
  
 [Servizi di hosting](hosting-services.md)  
  
 [Creazione di client](building-clients.md)  
  
 [Introduzione all'estendibilità](introduction-to-extensibility.md)  
  
 [Amministrazione e diagnostica](./diagnostics/index.md)  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione WCF di base](basic-wcf-programming.md)
- [Panoramica dei concetti](conceptual-overview.md)
- [Dettagli delle funzionalità di WCF](./feature-details/index.md)
