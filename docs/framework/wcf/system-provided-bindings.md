---
title: Associazioni fornite dal sistema
description: Informazioni su tutte le associazioni Windows Communication Foundation (WCF) fornite dal sistema.
ms.date: 06/05/2018
helpviewer_keywords:
- bindings [WCF], system-provided
ms.assetid: 2c243746-45ce-4588-995e-c17126a579a6
ms.openlocfilehash: 3c6c6b628d208aede8c547dcfa66fc189a26ae01
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569602"
---
# <a name="system-provided-bindings"></a>Associazioni fornite dal sistema

Le associazioni specificano il meccanismo di comunicazione da utilizzare durante la comunicazione con un endpoint e indicano come collegarsi a un endpoint. Un'associazione contiene gli elementi seguenti:

- Lo stack del protocollo determina la sicurezza, l'affidabilità e le impostazioni del flusso di contesto da utilizzare per i messaggi inviati all'endpoint.

- Il trasporto determina il protocollo di trasporto sottostante da utilizzare quando si inviano messaggi all'endpoint, ad esempio, TCP o HTTP.

- La codifica determina la codifica di trasmissione da usare per i messaggi inviati all'endpoint, ad esempio, testo/XML, binaria o MTOM (Message Transmission Optimization Mechanism).

 Questo articolo presenta tutte le associazioni Windows Communication Foundation (WCF) fornite dal sistema. Se nessuna di queste associazioni soddisfa esattamente i criteri per l'applicazione, è possibile creare un'associazione personalizzata. Per altre informazioni sulla creazione di associazioni personalizzate, vedere [Associazioni personalizzate](./extending/custom-bindings.md).

 Un'associazione protetta e interoperabile che supporta il protocollo WS-Federation consente alle organizzazioni di una federazione di autenticare e autorizzare gli utenti in modo efficiente.

> [!IMPORTANT]
> Selezionare sempre un'associazione che include la sicurezza. Per impostazione predefinita, la sicurezza è attivata per tutte le associazioni, tranne che per [\<basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md). Se non si seleziona un'associazione protetta o se si disattiva la sicurezza, assicurarsi di proteggere i dati in altro modo, ad esempio archiviandoli in un centro dati protetto o in una rete isolata.

> [!IMPORTANT]
> Non utilizzare mai contratti duplex con associazioni che non supportano la sicurezza o che hanno la sicurezza disattivata, a meno che non si proteggano i dati in altro modo.

Con WCF sono in dotazione le associazioni seguenti:

|Binding|Elemento di configurazione|Descrizione|
|-------------|---------------------------|-----------------|
|<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md)|Associazione idonea per la comunicazione con servizi Web conformi a WS-Basic Profile, ad esempio servizi basati su servizi Web ASP.NET (ASMX). Questa associazione utilizza HTTP come trasporto e testo/XML come codifica dei messaggi predefinita.|
|<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md)|Un'associazione protetta e interoperabile adatta per contratti di servizio non duplex.|
|<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Associazione protetta e interoperabile adatta per contratti di servizio duplex o per la comunicazione tramite intermediari SOAP.|
|<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Associazione protetta e interoperabile che supporta il protocollo WS-Federation, che consente alle organizzazioni di una federazione di autenticare e autorizzare gli utenti in modo efficiente.|
|<xref:System.ServiceModel.NetHttpBinding>|[\<netHttpBinding>](../configure-apps/file-schema/wcf/nethttpbinding.md)|Associazione progettata per utilizzare i servizi HTTP o WebSocket che utilizza la codifica binaria per impostazione predefinita.|
|<xref:System.ServiceModel.NetHttpsBinding>|[\<netHttpsBinding>](../configure-apps/file-schema/wcf/nethttpsbinding.md)|Associazione protetta progettata per utilizzare i servizi HTTP o WebSocket che utilizza la codifica binaria per impostazione predefinita.|
|<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md)|Associazione protetta e ottimizzata adatta per le comunicazioni tra applicazioni WCF da un computer a un altro.|
|<xref:System.ServiceModel.NetNamedPipeBinding>|[\<netNamedPipeBinding>](../configure-apps/file-schema/wcf/netnamedpipebinding.md)|Associazione protetta, affidabile e ottimizzata adatta per la comunicazione tra applicazioni WCF in un computer.|
|<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding>](../configure-apps/file-schema/wcf/netmsmqbinding.md)|Associazione in coda adatta per la comunicazione tra applicazioni WCF da un computer a un altro.|
|<xref:System.ServiceModel.NetPeerTcpBinding>|[\<netPeerTcpBinding>](../configure-apps/file-schema/wcf/netpeertcpbinding.md)|Associazione che consente comunicazioni sicure tra più computer.|
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|[\<msmqIntegrationBinding>](../configure-apps/file-schema/wcf/msmqintegrationbinding.md)|Associazione adatta per la comunicazione da un computer a un altro tra un'applicazione WCF e applicazioni di Accodamento messaggi esistenti.|
|<xref:System.ServiceModel.BasicHttpContextBinding>|[\<basicHttpContextBinding>](../configure-apps/file-schema/wcf/basichttpcontextbinding.md)|Associazione adatta per la comunicazione con servizi Web conformi a WS-Basic Profile che consente l'uso di cookie HTTP per lo scambio del contesto.|
|<xref:System.ServiceModel.NetTcpContextBinding>|[\<netTcpContextBinding>](../configure-apps/file-schema/wcf/nettcpcontextbinding.md)|Associazione sicura e ottimizzata adatta per le comunicazioni da un computer a un altro tra applicazioni WCF. Consente l'uso delle intestazioni SOAP per lo scambio del contesto.|
|<xref:System.ServiceModel.WebHttpBinding>|[\<webHttpBinding>](../configure-apps/file-schema/wcf/webhttpbinding.md)|Associazione usata per configurare endpoint per servizi Web WCF esposti tramite richieste HTTP anziché tramite messaggi SOAP.|
|<xref:System.ServiceModel.WSHttpContextBinding>|[\<wsHttpContextBinding>](../configure-apps/file-schema/wcf/wshttpcontextbinding.md)|Associazione protetta e interoperativa adatta per contratti di servizio non duplex che consente l'uso delle intestazioni SOAP per lo scambio del contesto.|
|<xref:System.ServiceModel.UdpBinding>|[\<udpBinding>](../configure-apps/file-schema/wcf/udpbinding.md)|Associazione da utilizzare quando si invia un burst di messaggi semplici a numerosi client contemporaneamente.|

 Nella tabella seguente sono riportate le funzionalità di ogni associazione fornita dal sistema: Le associazioni sono riportate nelle colonne della tabella, mentre le funzionalità sono elencate nelle righe e descritte in una seconda tabella. Nella tabella seguente viene fornita una chiave per le abbreviazioni delle associazioni utilizzate. Per selezionare un'associazione, stabilire qual è la colonna che soddisfa tutte le funzioni della riga necessarie.

|Binding|Interoperabilità|Sicurezza (predefinita)|Sessione<br />(Predefinito)|Transazioni|Duplex|Codifica (predefinita)|Flusso<br />(Predefinito)|
|-------------|----------------------|--------------------------|-----------------------------|------------------|------------|--------------------------|-------------------------------|
|<xref:System.ServiceModel.BasicHttpBinding>|Basic Profile 1.1|(None), Transport, Message, misto|(Nessuno)|(Nessuno)|N/D|Text, (MTOM)|Yes<br />(memorizzato nel buffer)|
|<xref:System.ServiceModel.WSHttpBinding>|WS|Transport, (Message), misto|(None), sessione affidabile, sessione di sicurezza|(None), sì|N/D|(Text), MTOM|No|
|<xref:System.ServiceModel.WSDualHttpBinding>|WS|(Message), None|(Sessione affidabile), sessione di sicurezza|(None), sì|Yes|(Text), MTOM|No|
|<xref:System.ServiceModel.WSFederationHttpBinding>|WS-Federation|(Message), misto, None|(None), sessione affidabile, sessione di sicurezza|(None), sì|No|(Text), MTOM|No|
|<xref:System.ServiceModel.NetHttpBinding>|.NET|(None), Transport, Message, TransportWithMessageCredential, TransportCredentialOnly|Vedere la nota più avanti|nessuno|Vedere la nota più avanti|(Binario), testo, MTOM|Sì (memorizzato nel buffer)|
|<xref:System.ServiceModel.NetHttpsBinding>|.NET|(Transport), TransportWithMessageCredential|Vedere la nota più avanti|nessuno|Vedere la nota più avanti|(Binario), testo, MTOM|Yes<br />(memorizzato nel buffer)|
|<xref:System.ServiceModel.NetTcpBinding>|.NET|(Transport), Message, None, misto|(Transport), sessione affidabile, sessione di sicurezza|(None), sì|Yes|Binario|Yes<br />(memorizzato nel buffer)|
|<xref:System.ServiceModel.NetNamedPipeBinding>|.NET|(Transport), None|None, (Transport)|(None), sì|Yes|Binario|Yes<br />(memorizzato nel buffer)|
|<xref:System.ServiceModel.NetMsmqBinding>|.NET|Message, (Transport), None|(None), Transport|None, (sì)|No|Binario|No|
|<xref:System.ServiceModel.NetPeerTcpBinding>|Peer|(Transport)|(Nessuno)|(Nessuno)|Yes||No|
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|MSMQ|(Transport)|(Nessuno)|None, (sì)|N/D|N/D|No|
|<xref:System.ServiceModel.BasicHttpContextBinding>|Basic Profile 1.1|(None), Transport, Message, misto|(Nessuno)|(Nessuno)|N/D|Text, (MTOM)|Yes<br />(memorizzato nel buffer)|
|<xref:System.ServiceModel.NetTcpContextBinding>|.NET|(Transport), Message, None, misto|(Transport), sessione affidabile, sessione di sicurezza|(None), sì|Yes|Binario|Yes<br />(memorizzato nel buffer)|
|<xref:System.ServiceModel.WSHttpContextBinding>|WS|Transport, (Message), misto|(None), sessione affidabile, sessione di sicurezza|(None), sì|N/D|Text, (MTOM)|No|
|<xref:System.ServiceModel.UdpBinding> <br /><br /> **Nota:**  L'interoperabilità può essere ottenuta implementando la specifica standard SOAP-over-UDP implementata da questa associazione.|.NET|(Nessuno)|(Nessuno)|(Nessuno)|N/D|(Text)|No|

> [!IMPORTANT]
> <xref:System.ServiceModel.NetHttpBinding> è un'associazione progettata per usare i servizi HTTP o WebSocket e usa la codifica binaria per impostazione predefinita. <xref:System.ServiceModel.NetHttpBinding> rileva se viene usato con un contratto request/reply o un contratto duplex e modifica il proprio comportamento di conseguenza. Usa HTTP per i contratti request/reply e WebSockets per i contratti duplex. Questo comportamento può essere sottoposto a override utilizzando il <xref:System.ServiceModel.Channels.WebSocketTransportUsage> impostazioni dell'associazione: WhenDuplex: si tratta del valore predefinito e si comporta come descritto in precedenza. Never: impedisce l'uso di WebSockets. Il tentativo di usare un contratto duplex con questa impostazione genera un'eccezione. Always: forza l'uso di WebSockets anche per i contratti request/reply. NetHttpBinding supporta sessioni affidabili sia in modalità HTTP sia in modalità WebSocket. Nella modalità WebSocket, le sessioni vengono fornite dal trasporto.

 Nella tabella seguente sono spiegate le funzionalità elencate nella tabella precedente.

|Funzionalità|Descrizione|
|-------------|-----------------|
|Tipo di interoperabilità|Denomina il protocollo o la tecnologia con cui l'associazione assicura l'interoperatività.|
|Sicurezza|Specifica come il canale viene protetto:<br />-None: Il messaggio SOAP non è protetto e il client non è autenticato.<br />-Transport: Requisiti di sicurezza sono soddisfatti a livello di trasporto.<br />-Messaggio: Requisiti di sicurezza sono soddisfatti a livello di messaggio.<br />-Mista: Le attestazioni sono contenute nel messaggio. requisiti di integrità e riservatezza sono soddisfatti dal livello di trasporto.|
|Sessione|Specifica se questa associazione supporta contratti di sessione.|
|Transazioni|Specifica se le transazioni sono attivate.|
|Duplex|Specifica se sono supportati contratti duplex. Si noti che questa funzionalità richiede il supporto delle sessioni nell'associazione.|
|Codifica|Specifica il formato di trasmissione del messaggio. I valori consentiti includono:<br />- Text: ad esempio UTF-8.<br />- Binary<br />-MTOM (MTOM): Un metodo per la codifica in modo efficiente elementi XML binari all'interno del contesto di una SOAP envelope.|
|Flusso|Specifica se il flusso è supportato per i messaggi in ingresso e in uscita. Utilizzare la proprietà `TransferMode` nell'associazione per impostare il valore. I valori consentiti includono:<br />- <xref:System.ServiceModel.TransferMode.Buffered>: I messaggi di richiesta e risposta vengono entrambi memorizzati nel buffer.<br />- <xref:System.ServiceModel.TransferMode.Streamed>: I messaggi di richiesta e risposta vengono entrambi inviati nel flusso.<br />- <xref:System.ServiceModel.TransferMode.StreamedRequest>: Il messaggio di richiesta viene inviato nel flusso e quello di risposta viene memorizzato nel buffer.<br />- <xref:System.ServiceModel.TransferMode.StreamedResponse>: Il messaggio di richiesta viene memorizzato nel buffer e quello di risposta viene inviato nel flusso.|

## <a name="see-also"></a>Vedere anche

- [Panoramica della creazione di endpoint](endpoint-creation-overview.md)
- [Uso di associazioni per configurare servizi e client](using-bindings-to-configure-services-and-clients.md)
- [Programmazione WCF di base](basic-wcf-programming.md)
