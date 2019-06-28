---
title: 'Endpoint: indirizzi, associazioni e contratti'
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: d224535bb266d0a3673359388c6c211103df7374
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424853"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a>Endpoint: indirizzi, associazioni e contratti
Tutte le comunicazioni con un servizio Windows Communication Foundation (WCF) viene eseguita tramite il *endpoint* del servizio. Gli endpoint forniscono ai client l'accesso alla funzionalità offerta da un servizio WCF.  
  
 Ogni endpoint è costituito da quattro proprietà:  
  
- Un indirizzo che indica dove si trova l'endpoint.  
  
- Un'associazione che specifica in che modo un client può comunicare con l'endpoint.  
  
- Un contratto che identifica le operazioni disponibili.  
  
- Un set di comportamenti che specificano dettagli di implementazione locali dell'endpoint.  
  
 In questo argomento viene illustrata questa struttura di endpoint e viene illustrato come viene rappresentato nel modello a oggetti WCF.  
  
## <a name="the-structure-of-an-endpoint"></a>Struttura di un endpoint  
 Ogni endpoint è costituito dagli elementi seguenti:  
  
- Indirizzo: L'indirizzo identifica l'endpoint in modo univoco e indica a potenziali consumer del servizio in cui si trova. È rappresentato nel modello a oggetti WCF dal <xref:System.ServiceModel.EndpointAddress> classe. Una classe <xref:System.ServiceModel.EndpointAddress> contiene:  
  
    - Una proprietà <xref:System.ServiceModel.EndpointAddress.Uri%2A>, che rappresenta l'indirizzo del servizio.  
  
    - Una proprietà <xref:System.ServiceModel.EndpointAddress.Identity%2A>, che rappresenta l'identità di sicurezza del servizio e una raccolta di intestazioni di messaggio facoltative. Le intestazioni di messaggio facoltative vengono utilizzate per fornire ulteriori informazioni di indirizzamento più dettagliate, per identificare o interagire con l'endpoint.  
  
     Per altre informazioni, vedere [che specifica un indirizzo Endpoint](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
- Binding: L'associazione specifica la modalità di comunicazione con l'endpoint. vale a dire:  
  
    - Il protocollo di trasporto da utilizzare (ad esempio, TCP o HTTP).  
  
    - La codifica da utilizzare per i messaggi (ad esempio, testo o binaria).  
  
    - I necessari requisiti di sicurezza (ad esempio, la protezione dei messaggi SSL o SOAP).  
  
     Per altre informazioni, vedere [panoramica delle associazioni WCF](../../../../docs/framework/wcf/bindings-overview.md). Un'associazione è rappresentata nel modello a oggetti WCF dalla classe di base astratta <xref:System.ServiceModel.Channels.Binding>. Per la maggior parte degli scenari, gli utenti possono utilizzare una delle associazioni fornite dal sistema. Per altre informazioni, vedere [System-provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
- Contratti: Il contratto delinea la funzionalità che l'endpoint espone al client. Un contratto specifica:  
  
    - Quali operazioni possono essere chiamate da un client.  
  
    - La forma del messaggio.  
  
    - Il tipo di parametri di input o di dati necessario per chiamare l'operazione.  
  
    - Il tipo di elaborazione o di messaggio di risposta che il client può aspettarsi.  
  
     Per altre informazioni sulla definizione di un contratto, vedere [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
- Comportamenti: È possibile usare i comportamenti dell'endpoint per personalizzare il comportamento dell'endpoint del servizio locale. I comportamenti dell'endpoint realizzano questo obiettivo partecipando nel processo di creazione di un runtime WCF. Un esempio di comportamento dell'endpoint è rappresentato dalla proprietà <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, che consente di specificare un indirizzo di ascolto diverso dall'indirizzo SOAP o WSDL (Web Services Description Language). Per altre informazioni, vedere [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).  
  
## <a name="defining-endpoints"></a>Definizione di endpoint  
 È possibile specificare l'endpoint di un servizio in modo imperativo, tramite codice, o in modo dichiarativo, tramite la configurazione. Per altre informazioni, vedere [Procedura: Creare un Endpoint del servizio nella configurazione](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) e [come: Creare un Endpoint del servizio nel codice](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 Contenuto della sezione viene illustrato lo scopo di associazioni, endpoint e indirizzi; viene descritto come configurare un'associazione e un endpoint e viene dimostrato come utilizzare il comportamento `ClientVia` e la proprietà `ListenUri`.  
  
 [Indirizzi](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 Viene descritto come vengono indirizzati gli endpoint in WCF.  
  
 [Associazioni](../../../../docs/framework/wcf/feature-details/bindings.md)  
 Viene descritto come vengono utilizzate le associazioni per specificare i dettagli sul trasporto, la codifica e il protocollo necessari per consentire la comunicazione tra client e servizi.  
  
 [Contratti](../../../../docs/framework/wcf/feature-details/contracts.md)  
 Viene descritto in che modo i contratti definiscono i metodi di un servizio.  
  
 [Procedura: Creare un Endpoint del servizio nella configurazione](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 Viene descritto come creare un endpoint del servizio nella configurazione.  
  
 [Procedura: Creare un Endpoint del servizio nel codice](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 Viene descritto come creare un endpoint del servizio nel codice.  
  
 [Procedura: Usare Svcutil.exe per convalidare il codice del servizio compilato](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 Viene descritto come rilevare errori in implementazioni del servizio e le configurazioni senza ospitare il servizio utilizzando il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione dei servizi](../../../../docs/framework/wcf/configuring-services.md)
- [Estensione delle associazioni](../../../../docs/framework/wcf/extending/extending-bindings.md)
