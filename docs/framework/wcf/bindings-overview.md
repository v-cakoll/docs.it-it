---
title: Panoramica sulle associazioni di Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], overview
ms.assetid: cfb5842f-e0f9-4c56-a015-f2b33f258232
ms.openlocfilehash: a8593c5dce30fc71750515ccedb4fc9cce9a4868
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64652108"
---
# <a name="windows-communication-foundation-bindings-overview"></a>Panoramica sulle associazioni di Windows Communication Foundation
Le associazioni sono oggetti che vengono utilizzati per specificare i dettagli di comunicazione necessarie per connettersi all'endpoint di un servizio Windows Communication Foundation (WCF). Ogni endpoint in un servizio WCF richiede un'associazione essere specificato bene. Questo argomento descrive i tipi dei dettagli di comunicazione definiti dalle associazioni, gli elementi di un'associazione, le associazioni incluse in WCF e come specificare un'associazione per un endpoint.  
  
## <a name="what-a-binding-defines"></a>Elementi definiti da un'associazione  
 Le informazioni presenti in un'associazione possono essere molto semplici o molto complesse. L'associazione più semplice specifica solo il protocollo di trasporto (ad esempio HTTP) che deve essere usato per connettersi all'endpoint. In termini più generali, le informazioni contenute in un'associazione sulla modalità di connessione a un endpoint rientrano in una delle categorie seguenti.  
  
 Protocolli  
 Determina il meccanismo di sicurezza usato: la funzionalità di messaggistica affidabile o le impostazioni di flusso del contesto della transazione.  
  
 Codifica  
 Determina la codifica del messaggio (ad esempio, testo o binario).  
  
 Trasporto  
 Determina il protocollo di trasporto sottostante da usare (ad esempio, TCP o HTTP).  
  
## <a name="the-elements-of-a-binding"></a>Elementi di un'associazione  
 Un'associazione è essenzialmente costituita da un stack ordinato di elementi di associazione, ognuno dei quali specifica parte delle informazioni di comunicazione necessarie per connettersi a un endpoint del servizio. I due livelli più bassi nello stack sono entrambi necessari. Alla base dello stack c'è l'elemento di associazione di trasporto e immediatamente al di sopra di questo c'è l'elemento che contiene le specifiche di codifica dei messaggi. Gli elementi di associazione facoltativi che specificano gli altri protocolli di comunicazione sono disposti sopra questi due elementi obbligatori. Per altre informazioni su questi elementi di associazione e il relativo ordinamento corretto, vedere [associazioni personalizzate](../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="system-provided-bindings"></a>Associazioni fornite dal sistema  
 Le informazioni in un'associazione possono essere complesse e alcune impostazioni potrebbero non essere compatibili con altre. Per questo motivo, WCF include un set di associazioni fornite dal sistema. Queste associazioni sono progettate per soddisfare la maggior parte dei requisiti delle applicazioni. Le classi seguenti rappresentano alcuni esempi di associazioni fornite dal sistema:  
  
- <xref:System.ServiceModel.BasicHttpBinding>: Un'associazione di protocollo HTTP adatta alla connessione ai servizi Web conformi a WS-I specifica Basic Profile (ad esempio, servizi Web ASP.NET basata sui servizi).  
  
- <xref:System.ServiceModel.WSHttpBinding>: Un'associazione interoperativa adatta per la connessione agli endpoint conformi a WS-* protocolli.  
  
- <xref:System.ServiceModel.NetNamedPipeBinding>: Usa il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] per connettersi agli altri endpoint WCF nello stesso computer.  
  
- <xref:System.ServiceModel.NetMsmqBinding>: Usa il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] per creare connessioni di messaggi in coda con altri endpoint WCF.  

- <xref:System.ServiceModel.NetTcpBinding>: Questa associazione offre prestazioni più elevate rispetto a binding HTTP ed è ideale per l'uso in una rete locale.
  
 Per un elenco completo, con le relative descrizioni, di tutte le associazioni fornita da WCF, vedere [System-provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).  
  
## <a name="using-your-own-bindings"></a>Uso di associazioni proprie  
 Se nessuna delle associazioni fornite dal sistema ha la giusta combinazione di funzionalità richieste da un'applicazione di servizio, è possibile creare una propria associazione. È possibile ottenere questo risultato in due modi. È possibile creare una nuova associazione da elementi di associazione preesistenti usando un oggetto <xref:System.ServiceModel.Channels.CustomBinding> o è possibile creare un'associazione completamente definita dall'utente derivandola dall'associazione <xref:System.ServiceModel.Channels.Binding>. Per altre informazioni sulla creazione di un'associazione utilizzando questi due approcci, vedere [associazioni personalizzate](../../../docs/framework/wcf/extending/custom-bindings.md) e [associazioni Creating User-Defined](../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
## <a name="using-bindings"></a>Uso di associazioni  
 L'utilizzo di associazioni comporta due passaggi di base:  
  
1. Selezionare o definire un'associazione. Il metodo più semplice è scegliere una delle associazioni fornite dal sistema incluse con WCF e usarlo con le impostazioni predefinite. È inoltre possibile scegliere un'associazione fornita dal sistema e reimpostarne i valori delle proprietà per adattarli ai propri requisiti. In alternativa, è possibile creare un'associazione personalizzata o un'associazione definita dall'utente, per avere un grado più elevato di controllo e personalizzazione.  
  
2. Creare un endpoint che usa l'associazione selezionata o definita.  
  
## <a name="code-and-configuration"></a>Codice e configurazione  
 È possibile definire associazioni in due modi, tramite il codice o la configurazione. Questi due approcci non variano a seconda che si stia usando un'associazione fornita dal sistema o un'associazione personalizzata. In generale, l'uso del codice garantisce il controllo completo sulla definizione di un'associazione in fase di progettazione. Usando la configurazione, d'altra parte, consente a un amministratore di sistema o l'utente di un servizio WCF o un client per modificare i parametri di un'associazione senza dover ricompilare l'applicazione di servizio. Questa flessibilità è spesso opportuno poiché non è possibile stimare i requisiti specifici del computer in cui è necessario distribuire un'applicazione WCF. Se l'associazione e le informazioni di indirizzo vengono tenute fuori dal codice, esse possono cambiare senza che sia necessario ricompilare o ridistribuire l'applicazione. Si noti che le associazioni definite in codice vengono create dopo le associazioni specificate in configurazione, il che consente alle associazioni definite nel codice di sovrascrivere qualsiasi associazione definita nella configurazione.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di associazioni per configurare servizi e client](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
