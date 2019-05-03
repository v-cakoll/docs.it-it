---
title: Panoramica delle sessioni affidabili
ms.date: 03/30/2017
ms.assetid: a7fc4146-ee2c-444c-82d4-ef6faffccc2d
ms.openlocfilehash: 6dd90ef800daf236d77c419d48c0857ac2d78aa2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962656"
---
# <a name="reliable-sessions-overview"></a>Panoramica delle sessioni affidabili

Messaggistica affidabile SOAP di Windows Communication Foundation (WCF) offre l'affidabilità del trasferimento di messaggi end-to-end tra endpoint SOAP. Svolge questa funzione su reti inaffidabili risolvendo gli errori del trasporto e gli errori a livello di messaggio SOAP. In particolare, assicura il recapito basato sulla sessione, singolo e (facoltativamente) ordinato dei messaggi inviati su intermediari SOAP o del trasporto. Recapito basato sulla sessione vengono fornite per il raggruppamento di messaggi in una sessione con ordinamento facoltativo dei messaggi.

In questo argomento descrive le sessioni affidabili, come e quando utilizzarle e come proteggerle.

## <a name="wcf-reliable-sessions"></a>Sessioni affidabili WCF

Le sessioni affidabili WCF è un'implementazione della messaggistica di base a quanto definito dal protocollo WS-ReliableMessaging affidabile SOAP.

La messaggistica affidabile SOAP WCF fornisce una sessione affidabile end-to-end tra due endpoint, indipendentemente dal numero o tipo di intermediari che separano gli endpoint di messaggistica. Sono inclusi tutti gli intermediari del trasporto che non utilizzano SOAP (ad esempio, il proxy HTTP) o gli intermediari che utilizzano SOAP (ad esempio, i router basati su SOAP o bridge) che sono necessari per i messaggi tra gli endpoint. Supporta un canale di sessione affidabile *interattiva* comunicazione in modo che i servizi connessi da tale canale vengono eseguiti simultaneamente e scambiare ed elaborare messaggi in condizioni di bassa latenza, vale a dire, all'interno di relativamente brevi intervalli di tempo. Questo accoppiamento implica che questi componenti avanzamento o venga eseguito contemporaneamente, pertanto non è senza isolamento fornito tra di essi.

Una sessione affidabile maschera due tipi di errori:

- Gli errori a livello di messaggio SOAP, che includono messaggi persi o duplicati e messaggi che arrivano in un ordine diverso da quello di invio.

- Gli errori del trasporto.

Una sessione affidabile implementa il protocollo WS-ReliableMessaging e una finestra di trasferimento in memoria, per mascherare gli errori a livello di messaggio SOAP, e ristabilisce le connessioni in caso di errori del trasporto.

Una sessione affidabile assicura per i messaggi SOAP ciò che TCP assicura per i pacchetti IP. Una connessione socket TCP garantisce il trasferimento singolare in ordine dei pacchetti IP tra i nodi. Il canale affidabile garantisce lo stesso tipo di trasferimento affidabile, ma differisce dall'affidabilità del socket TCP nei modi seguenti:

- L'affidabilità è a livello di messaggio SOAP e non è relativa a un pacchetto di byte di dimensioni arbitrarie.

- L'affidabilità è transport-neutral, non solo per il trasferimento tramite TCP.

- L'affidabilità non è collegato a una sessione di trasporto specifico (ad esempio, la sessione offre una connessione TCP) e può usare più sessioni di trasporto contemporaneamente o in sequenza in base alla durata della sessione affidabile.

- La sessione affidabile viene stabilita tra gli endpoint SOAP mittente e destinatario, indipendentemente dal numero di connessioni del trasporto necessarie per la connettività tra di essi. In breve, l'affidabilità TCP termina dove termina di connessione del trasporto, mentre una sessione affidabile offre affidabilità end-to-end.

## <a name="reliable-sessions-and-bindings"></a>Sessioni affidabili e associazioni

Come accennato in precedenza, una sessione affidabile è neutra rispetto al trasporto. Inoltre, è possibile stabilire una sessione affidabile su molti modelli di scambio di messaggi, ad esempio request / reply o duplex. Una sessione affidabile di WCF viene esposto come proprietà di un set di associazioni.

Usare una sessione affidabile su endpoint che usano:

- Associazioni standard del trasporto basate su HTTP:

  - `WsHttpBinding` e contratti unidirezionali o request/reply di esposizione.

  - Quando si usa una sessione affidabile su un contratto di servizio semplice unidirezionale o request / reply.

  - `WsDualHttpBinding` e contratti unidirezionali, request/reply o duplex di esposizione.

  - `WsFederationHttpBinding` e contratti unidirezionali o request/reply di esposizione.

- Associazioni standard del trasporto basate su TCP:

  - `NetTcpBinding` e contratti unidirezionali, request/reply o duplex di esposizione.

Usare una sessione affidabile su qualsiasi altra associazione creando un'associazione personalizzata, ad esempio HTTPS (per altre informazioni sui problemi, vedere <a href="#reliable-sessions-and-security">sicurezza e le sessioni affidabili</a>) o un'associazione con named pipe.

Si può creare stack di una sessione affidabile su diversi tipi di canale sottostante e la forma del canale di sessione affidabile risultante varia. Nel client e nel server, il tipo di canale di sessione affidabile supportato dipende dal tipo di canale sottostante utilizzato. Nella tabella seguente sono elencati i tipi di canale di sessione supportati sul client come funzione del canale sottostante.

| Tipi di canale di sessione affidabile supportati&#8224; | `IRequestChannel` | `IRequestSessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :---------------: | :----------------------: | :--------------: | :---------------------: |
| `IOutputSessionChannel`                         | Yes               | Yes                      | Yes              | Yes                     |
| `IRequestSessionChannel`                        | Yes               | Yes                      | No               | No                      |
| `IDuplexSessionChannel`                         | No                | No                       | Yes              | Yes                     |

&#8224;I tipi di canale supportati sono i valori disponibili per il tipo generico `TChannel` valore del parametro che viene passato il <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelFactory%60%601%28System.ServiceModel.Channels.BindingContext%29> (metodo).

Nella tabella seguente sono elencati i tipi di canale di sessione supportati sul server come funzione del canale sottostante.

| Tipi di canale di sessione affidabile supportati&#8225; | `IReplyChannel` | `IReplySessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :-------------: | :--------------------: | :--------------: | :---------------------: |
| `IInputSessionChannel`                          | Yes             | Yes                    | Yes              | Yes                     |
| `IReplySessionChannel`                          | Yes             | Yes                    | No               | No                      |
| `IDuplexSessionChannel`                         | No              | No                     | Yes              | Yes                     |

&#8225;I tipi di canale supportati sono i valori disponibili per il tipo generico `TChannel` valore del parametro che viene passato il <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelListener%60%601%28System.ServiceModel.Channels.BindingContext%29> (metodo).

## <a name="reliable-sessions-and-security"></a>Sicurezza e le sessioni affidabili

Protezione di una sessione affidabile è importante per garantire che le parti che comunicano (servizio e client) vengano autenticate e che i messaggi scambiati nella sessione non vengono alterati. Inoltre, è importante garantire l'integrità di ogni singola sessione affidabile. Una sessione affidabile viene protetta mediante l'associazione a un contesto di sicurezza che ha rappresentato e gestito da un canale di sessione di sicurezza. Il canale di sicurezza fornisce una sessione di sicurezza. Per proteggere il messaggio nella sessione affidabile vengono quindi utilizzati i token di sicurezza scambiati durante la creazione della sessione.

Una volta una sessione affidabile su TCP-S, la sessione TCP viene associata alla sessione affidabile. Pertanto, la sicurezza del trasporto assicura che sicurezza è anche associata alla sessione affidabile. In questo caso, la riesecuzione della connessione viene disattivata.

L'unica eccezione si verifica in caso di utilizzo di HTTPS. La sessione di Secure Sockets Layer (SSL) non è associata alla sessione affidabile. Per questo motivo una minaccia, poiché le sessioni che condividono un contesto di sicurezza (la sessione SSL) non sono protette dagli altri; Ciò può o non costituire una minaccia reale a seconda dell'applicazione.

## <a name="using-reliable-sessions"></a>Grazie a sessioni sicure

Per utilizzare sessioni affidabili WCF, creare un endpoint con un'associazione che supporta una sessione affidabile. Usare una delle associazioni fornite dal sistema forniti da WCF con sessione affidabile attivata o creare un'associazione personalizzata che esegue questa operazione.

Le associazioni definite dal sistema che supportano e attivano una sessione affidabile per impostazione predefinita includono:

- <xref:System.ServiceModel.WSDualHttpBinding>

Le associazioni fornite dal sistema che supportano una sessione affidabile come opzione ma non abilita una per impostazione predefinita includono:

- <xref:System.ServiceModel.WSHttpBinding>

- <xref:System.ServiceModel.WSFederationHttpBinding>

- <xref:System.ServiceModel.NetTcpBinding>

Per un esempio di come creare un'associazione personalizzata, vedere [come: Creare un'associazione di sessione affidabile personalizzata con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).

Per informazioni sul binding WCF che supportano sessioni affidabili, vedere [System-provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).

## <a name="when-to-use-reliable-sessions"></a>Quando utilizzare sessioni affidabili

È importante capire quando utilizzare sessioni affidabili nell'applicazione. WCF supporta sessioni affidabili tra endpoint che sono contemporaneamente attivi e operativi. Se l'applicazione richiede uno degli endpoint non sia disponibile per un intervallo di tempo, quindi usare le code per realizzare l'affidabilità.

Se lo scenario richiede due endpoint connessi tramite TCP, TCP può essere sufficiente a fornire gli scambi di messaggi affidabili. Tuttavia, non è necessario usare una sessione affidabile, dal momento che TCP assicura che i pacchetti arrivino in ordine e una sola volta.

Se per lo scenario è presenti le caratteristiche seguenti, quindi è necessario considerare seriamente utilizza una sessione affidabile.

- Intermediari SOAP, ad esempio router SOAP

- Intermediari proxy o bridge di trasporto

- Connettività intermittente

- Sessioni su HTTP

## <a name="see-also"></a>Vedere anche

- [Uso di associazioni per configurare servizi e client](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [Sessioni affidabili WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md)
