---
title: Perché si consiglia gRPC per gli sviluppatori WCF - gRPC per gli sviluppatori WCF
description: Una discussione sul perché gRPC è una buona misura per gli sviluppatori WCF che vogliono migrare a architetture e piattaforme moderne.
ms.date: 09/02/2019
ms.openlocfilehash: 664781e94c24c1796eafa6a70eb28d453b530d66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147646"
---
# <a name="why-we-recommend-grpc-for-wcf-developers"></a>Perché gRPC è consigliato per gli sviluppatori WCF

Prima di approfondire il linguaggio e le tecniche di gRPC, vale la pena discutere perché gRPC è la soluzione giusta per gli sviluppatori di Windows Communication Foundation (WCF) che desiderano eseguire la migrazione a .NET Core.

## <a name="similarity-to-wcf"></a>Somiglianza con WCFSimilarity to WCF

Anche se l'implementazione e l'approccio sono diversi per gRPC, l'esperienza di sviluppo e utilizzo di servizi con gRPC dovrebbe essere intuitiva per gli sviluppatori WCF. L'obiettivo sottostante è lo stesso: rendere possibile il codice come se il client e il server si trovasse sulla stessa piattaforma, senza doversi preoccupare della rete.

Entrambe le piattaforme condividono il principio di dichiarazione e quindi l'implementazione di un'interfaccia, anche se il processo per dichiarare tale interfaccia è diverso. E come si vedrà nel capitolo 5, i diversi tipi di chiamate RPC che gRPC supporta mappare bene alle associazioni disponibili per i servizi WCF.

## <a name="benefits-of-grpc"></a>Vantaggi di gRPC

gRPC si trova al di sopra di altre soluzioni per i seguenti motivi.

### <a name="performance"></a>Prestazioni

L'utilizzo di HTTP/2 anziché di HTTP/1.1 rimuove il requisito per i messaggi leggibili dall'utente e utilizza invece il protocollo binario più piccolo e veloce. Questo è più efficiente per i computer da analizzare. HTTP/2 supporta anche le richieste multiplexing su una singola connessione. Questo supporto consente l'invio di risposte non appena sono pronte senza la necessità di attendere in una coda. (In HTTP/1.1, questo problema è noto come "head-of-line (HOL) blocco.") Hai bisogno di meno risorse quando usi gRPC, il che lo rende una buona soluzione da utilizzare per i dispositivi mobili e su reti più lente.

### <a name="interoperability"></a>Interoperabilità

Ci sono strumenti e librerie gRPC per tutti i principali linguaggi di programmazione e piattaforme, tra cui .NET, Java, Python, Go, C , Node.js, Swift, Dart, Ruby e PHP. Grazie al formato di filo binario Protocol Buffers e l'efficiente generazione di codice per ogni piattaforma, gli sviluppatori possono creare applicazioni performanti pur godendo di supporto cross-platform completo.

### <a name="usability-and-productivity"></a>Usabilità e produttività

gRPC è una soluzione RPC completa. Funziona in modo coerente su più lingue e piattaforme. Fornisce anche utensili eccellenti, con gran parte del codice boilerplate necessario generato automaticamente. Così più tempo sviluppatore viene liberato per concentrarsi sulla logica di business.

### <a name="streaming"></a>Streaming

gRPC ha uno streaming bidirezionale completo, che fornisce funzionalità simili ai servizi duplex completi di WCF. Lo streaming gRPC può funzionare su connessioni Internet regolari, servizi di bilanciamento del carico e dimensioni dei servizi.

### <a name="deadlinetimeouts-and-cancellation"></a>Scadenza/timeout e cancellazione

gRPC consente ai client di specificare un tempo massimo per il completamento di una RPC. Se la scadenza specificata viene superata, il server può annullare l'operazione indipendentemente dal client. Le scadenze e gli annullamenti possono essere propagati tramite ulteriori chiamate gRPC per applicare i limiti di utilizzo delle risorse. I client possono anche interrompere le operazioni quando viene superata una scadenza o prima, se necessario (ad esempio, a causa di un'interazione dell'utente).

### <a name="security"></a>Security

gRPC è implicitamente sicuro quando utilizza HTTP/2 su una connessione crittografata end-to-end TLS. Il supporto per l'autenticazione dei certificati client (vedere [il capitolo 6](security.md)) aumenta ulteriormente la sicurezza e l'attendibilità tra client e server.

>[!div class="step-by-step"]
>[Successivo](network-protocols.md)
>[precedente](protocol-buffers.md)
