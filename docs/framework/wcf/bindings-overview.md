---
title: Panoramica sulle associazioni di Windows Communication Foundation
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings [WCF], overview
ms.assetid: cfb5842f-e0f9-4c56-a015-f2b33f258232
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 58b3691c186dc6a33c94d9f8a1af96be488d67df
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="windows-communication-foundation-bindings-overview"></a>Panoramica sulle associazioni di Windows Communication Foundation
Le associazioni sono oggetti usati per specificare i dettagli di comunicazione necessari per connettersi all'endpoint di un servizio [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]. Ogni endpoint in un servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] richiede un'associazione per essere specificato bene. In questo argomento vengono illustrati di tipi di dettagli di comunicazione definiti dalle associazioni, gli elementi di un'associazione, le associazioni incluse in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e il modo in cui è possibile specificare un'associazione per un endpoint.  
  
## <a name="what-a-binding-defines"></a>Elementi definiti da un'associazione  
 Le informazioni presenti in un'associazione possono essere molto semplici o molto complesse. L'associazione più semplice specifica solo il protocollo di trasporto (ad esempio HTTP) che deve essere usato per connettersi all'endpoint. In termini più generali, le informazioni contenute in un'associazione sulla modalità di connessione a un endpoint rientrano in una delle categorie seguenti.  
  
 Protocolli  
 Determina il meccanismo di sicurezza usato: la funzionalità di messaggistica affidabile o le impostazioni di flusso del contesto della transazione.  
  
 Codifica  
 Determina la codifica del messaggio (ad esempio, testo o binario).  
  
 Trasporto  
 Determina il protocollo di trasporto sottostante da usare (ad esempio, TCP o HTTP).  
  
## <a name="the-elements-of-a-binding"></a>Elementi di un'associazione  
 Un'associazione è essenzialmente costituita da un stack ordinato di elementi di associazione, ognuno dei quali specifica parte delle informazioni di comunicazione necessarie per connettersi a un endpoint del servizio. I due livelli più bassi nello stack sono entrambi necessari. Alla base dello stack c'è l'elemento di associazione di trasporto e immediatamente al di sopra di questo c'è l'elemento che contiene le specifiche di codifica dei messaggi. Gli elementi di associazione facoltativi che specificano gli altri protocolli di comunicazione sono disposti sopra questi due elementi obbligatori. Per ulteriori informazioni su questi elementi di associazione e l'ordinamento corretto, vedere [associazioni personalizzate](../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="system-provided-bindings"></a>Associazioni fornite dal sistema  
 Le informazioni in un'associazione possono essere complesse e alcune impostazioni potrebbero non essere compatibili con altre. Per questo motivo, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] include un set di associazioni fornite dal sistema. Queste associazioni sono progettate per soddisfare la maggior parte dei requisiti delle applicazioni. Le classi seguenti rappresentano alcuni esempi di associazioni fornite dal sistema:  
  
-   <xref:System.ServiceModel.BasicHttpBinding>: associazione di protocollo HTTP adatta alla connessione a servizi Web conformi alla specifica WS-I Basic Profile (ad esempio, servizi basati sui servizi Web ASP.NET).  
  
-   <xref:System.ServiceModel.WSHttpBinding>: associazione interoperabile adatta alla connessione agli endpoint conformi ai protocolli WS-*.  
  
-   <xref:System.ServiceModel.NetNamedPipeBinding>: usa [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] per connettersi ad altri endpoint [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sullo stesso computer.  
  
-   <xref:System.ServiceModel.NetMsmqBinding>: usa [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] per creare connessioni dei messaggi in coda con altri endpoint [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 Per un elenco completo, con le descrizioni, di tutti i [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-purché binding, vedere [associazioni fornite dal sistema](../../../docs/framework/wcf/system-provided-bindings.md).  
  
## <a name="using-your-own-bindings"></a>Uso di associazioni proprie  
 Se nessuna delle associazioni fornite dal sistema ha la giusta combinazione di funzionalità richieste da un'applicazione di servizio, è possibile creare una propria associazione. È possibile ottenere questo risultato in due modi. È possibile creare una nuova associazione da elementi di associazione preesistenti usando un oggetto <xref:System.ServiceModel.Channels.CustomBinding> o è possibile creare un'associazione completamente definita dall'utente derivandola dall'associazione <xref:System.ServiceModel.Channels.Binding>. Per ulteriori informazioni sulla creazione di una propria associazione usando questi due approcci, vedere [associazioni personalizzate](../../../docs/framework/wcf/extending/custom-bindings.md) e [Creating User-Defined associazioni](../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
## <a name="using-bindings"></a>Uso di associazioni  
 L'utilizzo di associazioni comporta due passaggi di base:  
  
1.  Selezionare o definire un'associazione. Il metodo più facile consiste nello scegliere una delle associazioni fornite dal sistema incluse in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e usarla con le relative impostazioni predefinite. È inoltre possibile scegliere un'associazione fornita dal sistema e reimpostarne i valori delle proprietà per adattarli ai propri requisiti. In alternativa, è possibile creare un'associazione personalizzata o un'associazione definita dall'utente, per avere un grado più elevato di controllo e personalizzazione.  
  
2.  Creare un endpoint che usa l'associazione selezionata o definita.  
  
## <a name="code-and-configuration"></a>Codice e configurazione  
 È possibile definire associazioni in due modi, tramite il codice o la configurazione. Questi due approcci non variano a seconda che si stia usando un'associazione fornita dal sistema o un'associazione personalizzata. In generale, l'uso del codice garantisce il controllo completo sulla definizione di un'associazione in fase di progettazione. L'utilizzo della configurazione, d'altra parte, consente a un amministratore di sistema o l'utente di un servizio o client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] di modificare i parametri di un'associazione senza dovere ricompilare l'applicazione di servizio. Questa flessibilità è spesso utile in quando non è possibile prevedere in alcun modo i requisiti specifici per la distribuzione di un'applicazione [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Se l'associazione e le informazioni di indirizzo vengono tenute fuori dal codice, esse possono cambiare senza che sia necessario ricompilare o ridistribuire l'applicazione. Si noti che le associazioni definite in codice vengono create dopo le associazioni specificate in configurazione, il che consente alle associazioni definite nel codice di sovrascrivere qualsiasi associazione definita nella configurazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di associazioni per configurare servizi e client](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
