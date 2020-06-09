---
title: Panoramica delle sessioni affidabili
ms.date: 03/30/2017
ms.assetid: a7fc4146-ee2c-444c-82d4-ef6faffccc2d
ms.openlocfilehash: a85a34c5e2ec7928c01586e4b01cdf5e90e896a7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601088"
---
# <a name="reliable-sessions-overview"></a>Panoramica delle sessioni affidabili

La messaggistica affidabile SOAP Windows Communication Foundation (WCF) fornisce l'affidabilità del trasferimento di messaggi end-to-end tra gli endpoint SOAP. Svolge questa funzione su reti inaffidabili risolvendo gli errori del trasporto e gli errori a livello di messaggio SOAP. In particolare, assicura il recapito basato sulla sessione, singolo e (facoltativamente) ordinato dei messaggi inviati su intermediari SOAP o del trasporto. Il recapito basato sulla sessione consente di raggruppare i messaggi in una sessione con ordinamento facoltativo dei messaggi.

In questo argomento vengono descritte le sessioni affidabili, come e quando utilizzarle e come proteggerle.

## <a name="wcf-reliable-sessions"></a>Sessioni affidabili WCF

WCF Reliable Sessions è un'implementazione della messaggistica affidabile SOAP in base a quanto definito dal protocollo WS-ReliableMessaging.

La messaggistica affidabile SOAP WCF fornisce una sessione affidabile end-to-end tra due endpoint, indipendentemente dal numero o dal tipo di intermediari che separano gli endpoint di messaggistica. Sono inclusi eventuali intermediari di trasporto che non utilizzano SOAP (ad esempio, proxy HTTP) o intermediari che utilizzano SOAP, ad esempio router o Bridge basati su SOAP, necessari per il flusso dei messaggi tra gli endpoint. Un canale di sessione affidabile supporta la comunicazione *interattiva* , in modo che i servizi connessi da tale canale vengano eseguiti simultaneamente, scambiando ed elaborando i messaggi in condizioni di bassa latenza, ovvero in intervalli di tempo relativamente brevi. Questo accoppiamento significa che questi componenti fanno progredire insieme o hanno esito negativo, quindi non viene fornito alcun isolamento tra di essi.

Una sessione affidabile maschera due tipi di errori:

- Gli errori a livello di messaggio SOAP, che includono messaggi persi o duplicati e messaggi che arrivano in un ordine diverso da quello di invio.

- Gli errori del trasporto.

Una sessione affidabile implementa il protocollo WS-ReliableMessaging e una finestra di trasferimento in memoria, per mascherare gli errori a livello di messaggio SOAP, e ristabilisce le connessioni in caso di errori del trasporto.

Una sessione affidabile assicura per i messaggi SOAP ciò che TCP assicura per i pacchetti IP. Una connessione socket TCP garantisce il trasferimento singolare in ordine dei pacchetti IP tra i nodi. Il canale affidabile garantisce lo stesso tipo di trasferimento affidabile, ma differisce dall'affidabilità del socket TCP nei modi seguenti:

- L'affidabilità è a livello di messaggio SOAP e non è relativa a un pacchetto di byte di dimensioni arbitrarie.

- L'affidabilità è indipendente dal trasporto, non solo per il trasferimento su TCP.

- L'affidabilità non è associata a una particolare sessione di trasporto (ad esempio, la sessione fornita da una connessione TCP) e può utilizzare più sessioni di trasporto simultaneamente o in sequenza per la durata della sessione affidabile.

- La sessione affidabile viene stabilita tra gli endpoint SOAP mittente e destinatario, indipendentemente dal numero di connessioni del trasporto necessarie per la connettività tra di essi. In breve, l'affidabilità TCP termina in cui termina la connessione di trasporto, mentre una sessione affidabile fornisce un'affidabilità end-to-end.

## <a name="reliable-sessions-and-bindings"></a>Sessioni e associazioni affidabili

Come indicato in precedenza, una sessione affidabile è neutra per il trasporto. Inoltre, è possibile stabilire una sessione affidabile su molti modelli di scambio di messaggi, ad esempio Request/Reply o duplex. Una sessione affidabile WCF viene esposta come proprietà di un set di associazioni.

Usare una sessione affidabile sugli endpoint che usano:

- Associazioni standard del trasporto basate su HTTP:

  - `WsHttpBinding` e contratti unidirezionali o request/reply di esposizione.

  - Quando si usa una sessione affidabile su una richiesta/risposta o un semplice contratto di servizio unidirezionale.

  - `WsDualHttpBinding` e contratti unidirezionali, request/reply o duplex di esposizione.

  - `WsFederationHttpBinding` e contratti unidirezionali o request/reply di esposizione.

- Associazioni standard del trasporto basate su TCP:

  - `NetTcpBinding` e contratti unidirezionali, request/reply o duplex di esposizione.

Utilizzare una sessione affidabile in qualsiasi altro binding creando un'associazione personalizzata, ad esempio HTTPS (per ulteriori informazioni sui problemi, vedere <a href="#reliable-sessions-and-security">sessioni affidabili e sicurezza</a>) o un'associazione named pipe.

È possibile impilare una sessione affidabile su diversi tipi di canale sottostanti e la forma del canale della sessione affidabile risultante varia. Sul client e sul server, il tipo di canale di sessione affidabile supportato dipende dal tipo di canale sottostante utilizzato. Nella tabella seguente sono elencati i tipi di canale di sessione supportati sul client come funzione del canale sottostante.

| Tipi di canale di sessione affidabili supportati&#8224; | `IRequestChannel` | `IRequestSessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :---------------: | :----------------------: | :--------------: | :---------------------: |
| `IOutputSessionChannel`                         | Sì               | Sì                      | Sì              | Sì                     |
| `IRequestSessionChannel`                        | Sì               | Sì                      | No               | No                      |
| `IDuplexSessionChannel`                         | No                | No                       | Sì              | Sì                     |

&#8224;i tipi di canale supportati sono i valori disponibili per il `TChannel` valore del parametro generico passato al <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelFactory%60%601%28System.ServiceModel.Channels.BindingContext%29> metodo.

Nella tabella seguente sono elencati i tipi di canale di sessione supportati sul server come funzione del canale sottostante.

| Tipi di canale di sessione affidabili supportati&#8225; | `IReplyChannel` | `IReplySessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :-------------: | :--------------------: | :--------------: | :---------------------: |
| `IInputSessionChannel`                          | Sì             | Sì                    | Sì              | Sì                     |
| `IReplySessionChannel`                          | Sì             | Sì                    | No               | No                      |
| `IDuplexSessionChannel`                         | No              | No                     | Sì              | Sì                     |

&#8225;i tipi di canale supportati sono i valori disponibili per il `TChannel` valore del parametro generico passato al <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelListener%60%601%28System.ServiceModel.Channels.BindingContext%29> metodo.

## <a name="reliable-sessions-and-security"></a>Sessioni affidabili e sicurezza

La protezione di una sessione affidabile è importante per garantire che le parti che comunicano (servizio e client) siano autenticate e che i messaggi scambiati nella sessione non vengano manomessi. Inoltre, è importante garantire l'integrità di ogni singola sessione affidabile. Una sessione affidabile viene protetta mediante l'associazione a un contesto di sicurezza rappresentato e gestito da un canale di sessione di sicurezza. Il canale di sicurezza fornisce una sessione di sicurezza. Per proteggere il messaggio nella sessione affidabile vengono quindi utilizzati i token di sicurezza scambiati durante la creazione della sessione.

Quando una sessione affidabile è su TCP-S, la sessione TCP è associata alla sessione affidabile. Di conseguenza, la sicurezza del trasporto garantisce che la sicurezza sia legata anche alla sessione affidabile. In questo caso, la riesecuzione della connessione viene disattivata.

L'unica eccezione si verifica in caso di utilizzo di HTTPS. La sessione di Secure Sockets Layer (SSL) non è associata alla sessione affidabile. Questa situazione impone una minaccia perché le sessioni che condividono un contesto di sicurezza (la sessione SSL) non sono protette le une dalle altre; Questo potrebbe essere una minaccia reale a seconda dell'applicazione.

## <a name="using-reliable-sessions"></a>Uso di sessioni affidabili

Per utilizzare sessioni affidabili WCF, creare un endpoint con un'associazione che supporti una sessione affidabile. Utilizzare una delle associazioni fornite dal sistema fornite da WCF con la sessione affidabile abilitata o creare un'associazione personalizzata che esegue questa operazione.

Le associazioni definite dal sistema che supportano e attivano una sessione affidabile per impostazione predefinita includono:

- <xref:System.ServiceModel.WSDualHttpBinding>

Le associazioni fornite dal sistema che supportano una sessione affidabile come opzione, ma non ne abilitano una per impostazione predefinita, includono:

- <xref:System.ServiceModel.WSHttpBinding>

- <xref:System.ServiceModel.WSFederationHttpBinding>

- <xref:System.ServiceModel.NetTcpBinding>

Per un esempio di come creare un'associazione personalizzata, vedere [procedura: creare un'associazione di sessione affidabile personalizzata con https](how-to-create-a-custom-reliable-session-binding-with-https.md).

Per informazioni sulle associazioni WCF che supportano sessioni affidabili, vedere [associazioni fornite dal sistema](../system-provided-bindings.md).

## <a name="when-to-use-reliable-sessions"></a>Quando usare sessioni affidabili

È importante comprendere quando utilizzare sessioni affidabili nell'applicazione. WCF supporta sessioni affidabili tra endpoint che sono attivi e attivi nello stesso momento. Se l'applicazione richiede che uno degli endpoint non sia disponibile per un periodo di tempo, usare le code per ottenere l'affidabilità.

Se lo scenario richiede due endpoint connessi tramite TCP, il protocollo TCP potrebbe essere sufficiente per fornire scambi di messaggi affidabili. Sebbene non sia necessario utilizzare una sessione affidabile, il protocollo TCP garantisce che i pacchetti arrivino in ordine e solo una volta.

Se lo scenario ha una delle caratteristiche seguenti, è necessario considerare seriamente l'uso di una sessione affidabile.

- Intermediari SOAP, ad esempio i router SOAP

- Intermediari proxy o Bridge di trasporto

- Connettività intermittente

- Sessioni su HTTP

## <a name="see-also"></a>Vedere anche

- [Uso di associazioni per configurare servizi e client](../using-bindings-to-configure-services-and-clients.md)
- [Sessioni affidabili WS](../samples/ws-reliable-session.md)
