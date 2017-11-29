---
title: Panoramica delle sessioni affidabili
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7fc4146-ee2c-444c-82d4-ef6faffccc2d
caps.latest.revision: "30"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ddec86fac46da7a93d17ecd55f292471fac2ee5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="reliable-sessions-overview"></a>Panoramica delle sessioni affidabili

La messaggistica affidabile SOAP di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] garantisce l'affidabilità del trasferimento di messaggi end-to-end tra endpoint SOAP. Svolge questa funzione su reti inaffidabili risolvendo gli errori del trasporto e gli errori a livello di messaggio SOAP. In particolare, assicura il recapito basato sulla sessione, singolo e (facoltativamente) ordinato dei messaggi inviati su intermediari SOAP o del trasporto. Recapito basato sulla sessione fornisce per raggruppare i messaggi in una sessione con ordinamento facoltativo dei messaggi.

In questo argomento descrive le sessioni affidabili, come e quando utilizzarle e come proteggerle.

## <a name="wcf-reliable-sessions"></a>Sessioni affidabili WCF

Le sessioni affidabili [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sono un'implementazione della messaggistica affidabile SOAP, nel modo definito dal protocollo WS-ReliableMessaging.

La messaggistica affidabile SOAP di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornisce una sessione end-to-end affidabile tra due endpoint, indipendentemente dal numero o dal tipo di intermediari che separano gli endpoint di messaggistica. Sono inclusi tutti gli intermediari del trasporto che non utilizzano SOAP (ad esempio, il proxy HTTP) o gli intermediari che utilizzano SOAP (ad esempio bridge o router basati su SOAP) necessari per i messaggi tra gli endpoint. Un canale di sessione affidabile supporta *interattivo* comunicazione in modo che i servizi connessi da tale canale eseguiti contemporaneamente e scambiare ed elaborare messaggi in condizioni di bassa latenza, ovvero all'interno di relativamente brevi intervalli di tempo. Questo accoppiamento implica che questi componenti avanzamento o failover contemporaneamente, pertanto non c'è nessun isolamento fornito tra di essi.

Una sessione affidabile maschera due tipi di errori:

- Gli errori a livello di messaggio SOAP, che includono messaggi persi o duplicati e messaggi che arrivano in un ordine diverso da quello di invio.

- Gli errori del trasporto.

Una sessione affidabile implementa il protocollo WS-ReliableMessaging e una finestra di trasferimento in memoria, per mascherare gli errori a livello di messaggio SOAP, e ristabilisce le connessioni in caso di errori del trasporto.

Una sessione affidabile assicura per i messaggi SOAP ciò che TCP assicura per i pacchetti IP. Una connessione socket TCP garantisce il trasferimento singolare in ordine dei pacchetti IP tra i nodi. Il canale affidabile garantisce lo stesso tipo di trasferimento affidabile, ma differisce dall'affidabilità del socket TCP nei modi seguenti:

- L'affidabilità è a livello di messaggio SOAP e non è relativa a un pacchetto di byte di dimensioni arbitrarie.

- L'affidabilità è indipendente dal trasporto, non solo per il trasferimento tramite TCP.

- L'affidabilità non è correlato a una sessione di trasporto specifico (ad esempio, la sessione fornisce una connessione TCP) e possa usare più sessioni di trasporto contemporaneamente o in sequenza in base alla durata della sessione affidabile.

- La sessione affidabile viene stabilita tra gli endpoint SOAP mittente e destinatario, indipendentemente dal numero di connessioni del trasporto necessarie per la connettività tra di essi. In breve, l'affidabilità TCP termina dove termina di connessione del trasporto, mentre una sessione affidabile offre affidabilità end-to-end.

## <a name="reliable-sessions-and-bindings"></a>Sessioni affidabili e associazioni

Come accennato in precedenza, una sessione affidabile è neutra rispetto al trasporto. Inoltre, è possibile stabilire una sessione affidabile su molti modelli di scambio di messaggi, ad esempio request / reply o duplex. Oggetto [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sessione affidabile è esposto come proprietà di un set di associazioni.

Utilizzare una sessione affidabile su endpoint che utilizzano:

- Associazioni standard del trasporto basate su HTTP:

  - `WsHttpBinding` e contratti unidirezionali o request/reply di esposizione.

  - Quando si utilizza una sessione affidabile su un request / reply o un contratto di servizio semplice unidirezionale.

  - `WsDualHttpBinding` e contratti unidirezionali, request/reply o duplex di esposizione.

  - `WsFederationHttpBinding` e contratti unidirezionali o request/reply di esposizione.

- Associazioni standard del trasporto basate su TCP:

  - `NetTcpBinding` e contratti unidirezionali, request/reply o duplex di esposizione.

Utilizzare una sessione affidabile su qualsiasi altra associazione creando un'associazione personalizzata, ad esempio HTTPS (per ulteriori informazioni sui problemi, vedere <a href="#reliable-sessions-and-security">sessioni affidabili e protezione</a>) o un'associazione named pipe.

È possibile impilare una sessione affidabile su diversi tipi di canale sottostante e la forma del canale di sessione affidabile risultante varia. Il client che sul server, il tipo di canale di sessione affidabile supportato dipende dal tipo di canale sottostante utilizzato. Nella tabella seguente sono elencati i tipi di canale di sessione supportati sul client come funzione del canale sottostante.

| Tipi di canale di sessione affidabile supportati &#8224; | `IRequestChannel` | `IRequestSessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :---------------: | :----------------------: | :--------------: | :---------------------: |
| `IOutputSessionChannel`                         | Sì               | Sì                      | Sì              | Sì                     |
| `IRequestSessionChannel`                        | Sì               | Sì                      | No               | No                      |
| `IDuplexSessionChannel`                         | No                | No                       | Sì              | Sì                     |

&#8224; I tipi di canale supportati sono i valori disponibili per il modello generico `TChannel` valore del parametro viene passato il <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelFactory%60%601%28System.ServiceModel.Channels.BindingContext%29> metodo.

Nella tabella seguente sono elencati i tipi di canale di sessione supportati sul server come funzione del canale sottostante.

| Tipi di canale di sessione affidabile supportati &#8225; | `IReplyChannel` | `IReplySessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :-------------: | :--------------------: | :--------------: | :---------------------: |
| `IInputSessionChannel`                          | Sì             | Sì                    | Sì              | Sì                     |
| `IReplySessionChannel`                          | Sì             | Sì                    | No               | No                      |
| `IDuplexSessionChannel`                         | No              | No                     | Sì              | Sì                     |

&#8225; I tipi di canale supportati sono i valori disponibili per il modello generico `TChannel` valore del parametro viene passato il <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelListener%60%601%28System.ServiceModel.Channels.BindingContext%29> metodo.

## <a name="reliable-sessions-and-security"></a>Sessioni affidabili e protezione

La protezione di una sessione affidabile è importante assicurarsi che le parti in comunicazione (servizio e client) vengano autenticate e che i messaggi scambiati nella sessione non vengono alterati. Inoltre, è importante assicurare l'integrità di ogni singola sessione affidabile. Una sessione affidabile viene protetta mediante l'associazione a un contesto di sicurezza che ha rappresentato e gestito da un canale di sessione di sicurezza. Il canale di sicurezza fornisce una sessione di sicurezza. Per proteggere il messaggio nella sessione affidabile vengono quindi utilizzati i token di sicurezza scambiati durante la creazione della sessione.

Quando una sessione affidabile su TCP-S, la sessione TCP è associata alla sessione affidabile. Pertanto, la sicurezza del trasporto assicura che protezione è inoltre associata alla sessione affidabile. In questo caso, la riesecuzione della connessione viene disattivata.

L'unica eccezione si verifica in caso di utilizzo di HTTPS. La sessione di Secure Sockets Layer (SSL) non è associata alla sessione affidabile. Questo rappresenta una minaccia, poiché le sessioni che condividono un contesto di sicurezza (la sessione SSL) non sono protette da altra. Ciò può o non costituire una minaccia reale a seconda dell'applicazione.

## <a name="using-reliable-sessions"></a>Utilizzo di sessioni affidabili

Per utilizzare sessioni affidabili [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], creare un endpoint con un'associazione che supporti una sessione affidabile. Utilizzare una delle associazioni fornite dal sistema che [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] offre con la sessione affidabile attivata o creare un'associazione personalizzata che esegue questa operazione.

Le associazioni definite dal sistema che supportano e attivano una sessione affidabile per impostazione predefinita includono:

- <xref:System.ServiceModel.WSDualHttpBinding>

Le associazioni fornite dal sistema che supportano una sessione affidabile come opzione ma non attivano una per impostazione predefinita includono:

- <xref:System.ServiceModel.WSHttpBinding>

- <xref:System.ServiceModel.WSFederationHttpBinding>

- <xref:System.ServiceModel.NetTcpBinding>

Per un esempio di come creare un'associazione personalizzata, vedere [procedura: creare un'associazione di sessione affidabile personalizzata con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).

Per una discussione su [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] associazioni che supportano sessioni affidabili, vedere [associazioni fornite dal sistema](../../../../docs/framework/wcf/system-provided-bindings.md).

## <a name="when-to-use-reliable-sessions"></a>Quando utilizzare sessioni affidabili

È importante capire quando utilizzare sessioni affidabili nell'applicazione. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supporta sessioni affidabili tra endpoint che sono contemporaneamente attivi e operativi. Se l'applicazione richiede uno degli endpoint non sia disponibile per un periodo di tempo, quindi utilizzare le code per realizzare l'affidabilità.

Se lo scenario richiede due endpoint connesso tramite TCP, TCP può essere sufficiente a fornire gli scambi di messaggi affidabili. Tuttavia, non è necessario utilizzare una sessione affidabile, poiché TCP garantisce che i pacchetti arrivino in ordine e una sola volta.

Se lo scenario ha le caratteristiche seguenti, quindi è necessario considerare seriamente l'utilizzo di una sessione affidabile.

- Intermediari SOAP, ad esempio router SOAP

- Intermediari proxy o bridge di trasporto

- Connettività intermittente

- Sessioni su HTTP

## <a name="see-also"></a>Vedere anche

[Uso di associazioni per configurare servizi e client](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
[Sessioni affidabili WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md)
