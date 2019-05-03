---
title: Uso di associazioni per configurare servizi e client
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], using
ms.assetid: c39479c3-0766-4a17-ba4c-97a74607f392
ms.openlocfilehash: 3b4f00617418d5f84a0da5d0e531e1f671b58bb1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791378"
---
# <a name="using-bindings-to-configure-services-and-clients"></a>Uso di associazioni per configurare servizi e client
Le associazioni sono oggetti che specificano i dettagli di comunicazione necessari per connettersi a un endpoint. In particolare, le associazioni contengono le informazioni di configurazione usate per creare il client o il runtime del servizio definendo le specifiche dei trasporti, i formati di trasmissione (codifica del messaggio) e i protocolli da usare per il relativo endpoint o canale client. Per creare un servizio Windows Communication Foundation (WCF) funzionante, ogni endpoint nel servizio richiede un'associazione. In questo argomento viene illustrato cosa sono le associazioni, come vengono definite e come viene specificata una particolare associazione per un endpoint.  
  
## <a name="what-a-binding-defines"></a>Elementi definiti da un'associazione  
 Le informazioni presenti in un'associazione possono essere molto semplici o molto complesse. L'associazione più semplice specifica solo il protocollo di trasporto (ad esempio HTTP) che deve essere usato per connettersi all'endpoint. In termini più generali, le informazioni contenute in un'associazione sulla modalità di connessione a un endpoint rientrano in una delle categorie della tabella seguente.  
  
 Protocolli  
 Determina il meccanismo di sicurezza usato: la funzionalità di messaggistica affidabile o le impostazioni di flusso del contesto della transazione.  
  
 Trasporto  
 Determina il protocollo di trasporto sottostante da usare (ad esempio, TCP o HTTP).  
  
 Codifica  
 Determina la codifica del messaggio, ad esempio, testo/XML, binaria o MTOM (Message Transmission Optimization Mechanism), che determina il modo in cui i messaggi vengono rappresentati come flussi di byte durante la trasmissione.  
  
## <a name="system-provided-bindings"></a>Associazioni fornite dal sistema  
 WCF include un set di associazioni fornite dal sistema che sono progettate per soddisfare la maggior parte degli scenari e requisiti dell'applicazione. Le classi seguenti rappresentano alcuni esempi di associazioni fornite dal sistema:  
  
- <xref:System.ServiceModel.BasicHttpBinding>: Un'associazione di protocollo HTTP adatta alla connessione ai servizi Web conformi a WS-I Basic Profile 1.1 specifica (ad esempio, dei servizi Web ASP.NET [ASMX]-servizi basati su).  
  
- <xref:System.ServiceModel.WSHttpBinding>: Associazione adatta alla connessione agli endpoint conformi al Web di protocollo HTTP specifiche protocolli dei servizi.  
  
- <xref:System.ServiceModel.NetNamedPipeBinding>: Usa la codifica binaria .NET e le tecnologie congiunzione di frame con il trasporto di named pipe di Windows per connettersi ad altri endpoint WCF nello stesso computer.  
  
- <xref:System.ServiceModel.NetMsmqBinding>: Usa la codifica binaria .NET e le tecnologie in combinazione con l'accodamento messaggi (noto anche come MSMQ) di frame per creare connessioni di messaggi in coda con altri endpoint WCF.  
  
 Per un elenco completo delle associazioni fornite dal sistema, con le relative descrizioni, vedere [System-provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).  
  
## <a name="custom-bindings"></a>Associazioni personalizzate  
 Se la raccolta di associazioni fornite dal sistema non include la corretta combinazione di funzionalità richiesta da un'applicazione di servizio, è possibile creare un'associazione <xref:System.ServiceModel.Channels.CustomBinding>. Per altre informazioni sugli elementi di un <xref:System.ServiceModel.Channels.CustomBinding> associazione, vedere [ \<customBinding >](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) e [associazioni personalizzate](../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="using-bindings"></a>Uso di associazioni  
 L'utilizzo di associazioni comporta due passaggi di base:  
  
1. Selezionare o definire un'associazione. Il metodo più facile consiste nello scegliere una delle associazioni fornite dal sistema e usarla con le relative impostazioni predefinite. È inoltre possibile scegliere un'associazione fornita dal sistema e reimpostarne i valori delle proprietà per adattarli ai propri requisiti. In alternativa, è possibile creare un'associazione personalizzata e impostare ogni proprietà in base alle esigenze.  
  
2. Creare un endpoint che usa questa associazione.  
  
## <a name="code-and-configuration"></a>Codice e configurazione  
 È possibile definire o configurare associazioni tramite il codice o la configurazione. Questi due approcci sono indipendenti dal tipo di associazione usato, ad esempio, se si usa un'associazione fornita dal sistema o <xref:System.ServiceModel.Channels.CustomBinding>. In generale, l'uso del codice garantisce il controllo completo sulla definizione di un'associazione durante la compilazione. Usando la configurazione, d'altra parte, consente a un amministratore di sistema o l'utente di un servizio WCF o un client per modificare i parametri delle associazioni. Questa flessibilità è spesso opportuno poiché non è possibile stimare i requisiti specifici del computer e le condizioni in cui è necessario distribuire un'applicazione WCF della rete. Se le informazioni sull'associazione (e l'indirizzo) vengono separate dal codice, gli amministratori possono modificare i dettagli dell'associazione senza dover compilare o distribuire nuovamente l'applicazione. Si noti che se l'associazione viene definita nel codice, sovrascrive qualsiasi definizione basata sulla configurazione creata nel file di configurazione. Per esempi di questi approcci, vedere gli argomenti seguenti:  
  
- [Procedura: Ospitare un servizio WCF in un'applicazione gestita](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md) fornisce un esempio di creazione di un'associazione nel codice.  
  
- [Esercitazione: Creare un client Windows Communication Foundation](../../../docs/framework/wcf/how-to-create-a-wcf-client.md) fornisce un esempio di creazione di un client tramite configurazione.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della creazione di endpoint](../../../docs/framework/wcf/endpoint-creation-overview.md)
- [Procedura: Specificare un'associazione al servizio nella configurazione](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)
- [Procedura: Specificare un'associazione al servizio nel codice](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md)
- [Procedura: Specificare un'associazione Client nella configurazione](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)
- [Procedura: Specificare un'associazione al Client nel codice](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-code.md)
