---
title: Configurazione di associazioni fornite dal sistema
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], system-provided bindings
- WCF [WCF], system-provided bindings
- bindings [WCF], system-provided
ms.assetid: 443f8d65-f1f2-4311-83b3-4d8fdf7ccf16
ms.openlocfilehash: d6018c8339cb04471bf9ce0f2ee86e091e1d1e95
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597527"
---
# <a name="configuring-system-provided-bindings"></a>Configurazione di associazioni fornite dal sistema
Le associazioni specificano il meccanismo di comunicazione da utilizzare durante la comunicazione con un endpoint e indicano come collegarsi a un endpoint. Le associazioni sono costituite da elementi che definiscono il modo in cui i canali Windows Communication Foundation (WCF) sono sovrapposti per fornire le funzionalità di comunicazione necessarie. Un'associazione contiene tre tipi di elementi:  
  
- Elementi di associazione dei canali di protocollo che determinano la sicurezza, l'affidabilità, le impostazioni di flusso del contesto o i protocolli definiti dall'utente da utilizzare con i messaggi inviati all'endpoint.  
  
- Elementi di associazione del canale di trasporto, che determinano il protocollo di trasporto sottostante da utilizzare quando si inviano messaggi all'endpoint, ad esempio, TCP o HTTP.  
  
- Elementi di associazione della codifica dei messaggi, che determinano la codifica di trasmissione da utilizzare per i messaggi inviati all'endpoint, ad esempio, testo/XML, binari o MTOM (Message Transmission Optimization Mechanism).  
  
 In questo argomento vengono presentate tutte le associazioni di Windows Communication Foundation (WCF) fornite dal sistema. Se nessuna di esse soddisfa i requisiti specifici dell'applicazione, è possibile creare un'associazione utilizzando la classe <xref:System.ServiceModel.Channels.CustomBinding>. Per altre informazioni sulla creazione di associazioni personalizzate, vedere [Associazioni personalizzate](../extending/custom-bindings.md).  
  
> [!IMPORTANT]
> Selezionare un'associazione con la sicurezza attivata. Per impostazione predefinita, tutte le associazioni, tranne l'associazione <xref:System.ServiceModel.BasicHttpBinding>, hanno la sicurezza attivata. Se non si seleziona un'associazione protetta o se si disattiva la sicurezza, assicurarsi che gli scambi di rete siano protetti in qualche altro modo, ad esempio archiviandoli in un centro dati protetto o in una rete isolata.  
  
> [!IMPORTANT]
> Non utilizzare contratti duplex con associazioni che non supportano la sicurezza o che hanno la sicurezza disattivata, a meno che lo scambio di rete non sia protetto in altro modo.  
  
## <a name="system-provided-bindings"></a>Associazioni fornite dal sistema  
 Le associazioni seguenti vengono fornite con WCF.  
  
|Binding|Elemento di configurazione|Descrizione|  
|-------------|---------------------------|-----------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md)|Associazione idonea per comunicare con servizi Web conformi a WS-Basic Profile, ad esempio servizi basati su servizi Web ASP.NET (ASMX). Questa associazione utilizza HTTP come trasporto e testo/XML come codifica dei messaggi predefinita.|  
|<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)|Un'associazione protetta e interoperabile adatta per contratti di servizio non duplex.|  
|<xref:System.ServiceModel.WS2007HttpBinding>|[\<ws2007HttpBinding>](../../configure-apps/file-schema/wcf/ws2007httpbinding.md)|Associazione protetta e interoperabile che fornisce il supporto per le versioni corrette degli elementi di associazione <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession> e <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A>.|  
|<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Associazione protetta e interoperabile adatta per contratti di servizio duplex o per la comunicazione tramite intermediari SOAP.|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Associazione protetta e interoperabile che supporta il protocollo WS-Federation, che consente alle organizzazioni di una federazione di autenticare e autorizzare gli utenti in modo efficiente.|  
|<xref:System.ServiceModel.WS2007FederationHttpBinding>|[\<ws2007FederationHttpBinding>](../../configure-apps/file-schema/wcf/ws2007federationhttpbinding.md)|Associazione protetta e interoperabile che deriva da <xref:System.ServiceModel.WS2007HttpBinding> e supporta la sicurezza federata.|  
|<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md)|Associazione protetta e ottimizzata adatta per le comunicazioni tra applicazioni WCF da un computer a un altro.|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|[\<netNamedPipeBinding>](../../configure-apps/file-schema/wcf/netnamedpipebinding.md)|Associazione protetta, affidabile e ottimizzata adatta per la comunicazione tra applicazioni WCF in un computer.|  
|<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding>](../../configure-apps/file-schema/wcf/netmsmqbinding.md)|Associazione in coda adatta per la comunicazione tra applicazioni WCF da un computer a un altro.|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|[\<netPeerTcpBinding>](../../configure-apps/file-schema/wcf/netpeertcpbinding.md)|Associazione che consente comunicazioni protette tra più computer.|  
|<xref:System.ServiceModel.WebHttpBinding>|[\<webHttpBinding>](../../configure-apps/file-schema/wcf/webhttpbinding.md)|Associazione usata per configurare endpoint per servizi Web WCF esposti tramite richieste HTTP anziché tramite messaggi SOAP.|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|[\<msmqIntegrationBinding>](../../configure-apps/file-schema/wcf/msmqintegrationbinding.md)|Binding adatto per la comunicazione tra computer tra un'applicazione WCF e le applicazioni di Accodamento messaggi (noto anche come MSMQ) esistenti.|  
  
## <a name="binding-features"></a>Funzionalità di associazione  
 Nella tabella seguente sono riportate alcune delle funzionalità chiave di ogni associazione fornita dal sistema: Le associazioni sono riportate nella prima colonna, mentre le informazioni relative alle funzionalità sono descritte nella tabella. Nella tabella seguente viene fornita una chiave per le abbreviazioni delle associazioni utilizzate. Per selezionare un'associazione, stabilire qual è la colonna che soddisfa tutte le funzionalità della riga necessarie.  
  
|Binding|Interoperabilità|Modalità di sicurezza (impostazione predefinita)|Sessione<br /><br /> Valore predefinito.|Transazioni|Duplex|  
|-------------|----------------------|----------------------------------|-----------------------------|------------------|------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|Basic Profile 1.1|(None), Transport, Message, misto|None, (None)|(nessuna)|n/d|  
|<xref:System.ServiceModel.WSHttpBinding>|WS|None, Transport, (Message), misto|(None), Transport, sessione affidabile|(None), sì|n/d|  
|<xref:System.ServiceModel.WS2007HttpBinding>|WS-Security, WS-Trust, WS-SecureConversation, WS-SecurityPolicy|None, Transport, (Message), misto|(None), Transport, sessione affidabile|(None), sì|n/d|  
|<xref:System.ServiceModel.WSDualHttpBinding>|WS|None, (Message)|(Sessione affidabile)|(None), sì|Sì|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|WS-Federation|None, (Message), misto|(None), sessione affidabile|(None), sì|No|  
|<xref:System.ServiceModel.WS2007FederationHttpBinding>|WS-Federation|None, (Message), misto|(None), sessione affidabile|(None), sì|No|  
|<xref:System.ServiceModel.NetTcpBinding>|.NET|None, (Transport), Message,<br /><br /> Mixed|Sessione affidabile, (Transport)|(None), sì|Sì|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|.NET|None,<br /><br /> (Transport)|None, (Transport)|(None), sì|Sì|  
|<xref:System.ServiceModel.NetMsmqBinding>|.NET|None, Message, (Transport), Both|(nessuna)|(None), sì|No|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|Peer|None, Message, (Transport), misto|(nessuna)|(nessuna)|Sì|  
|<xref:System.ServiceModel.WebHttpBinding>|.Net|Nessuno, trasporto, TransportCredentialOnly|(nessuna)|(nessuna)|n/d|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|MSMQ|None, (Transport)|(nessuna)|(None), sì|n/d|  
  
 Nella tabella seguente sono spiegate le funzionalità elencate nella tabella precedente.  
  
|Funzionalità|Descrizione|  
|-------------|-----------------|  
|Tipo di interoperabilità|Denomina il protocollo o la tecnologia con cui l'associazione assicura l'interoperatività.|  
|Sicurezza|Specifica come il canale viene protetto:<br /><br /> -None: il messaggio SOAP non è protetto e il client non è autenticato.<br />-Transport: i requisiti di sicurezza sono soddisfatti a livello di trasporto.<br />-Message: i requisiti di sicurezza sono soddisfatti a livello di messaggio.<br />-Mixed: questa modalità di sicurezza è nota come `TransportWithMessageCredentials` . Gestisce le credenziali a livello di messaggio, mentre i requisiti di integrità e riservatezza sono soddisfatti dal livello di trasporto.<br />-Both: viene utilizzata la sicurezza a livello di messaggio e di trasporto. Questa possibilità è disponibile solo per <xref:System.ServiceModel.NetMsmqBinding>.|  
|Sessione|Specifica se questa associazione supporta contratti di sessione.|  
|Transazioni|Specifica se le transazioni sono attivate.|  
|Duplex|Specifica se sono supportati contratti duplex. Si noti che questa funzionalità richiede il supporto delle sessioni nell'associazione.|  
|Streaming|Specifica se il flusso dei messaggi è supportato.|  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla creazione di endpoint](../endpoint-creation-overview.md)
- [Uso di associazioni per configurare servizi e client](../using-bindings-to-configure-services-and-clients.md)
- [Programmazione WCF di base](../basic-wcf-programming.md)
