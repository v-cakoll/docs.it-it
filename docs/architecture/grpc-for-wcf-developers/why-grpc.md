---
title: Perché è consigliabile gRPC per gli sviluppatori WCF-gRPC per gli sviluppatori WCF
description: Descrizione del motivo per cui gRPC è una soluzione ideale per gli sviluppatori WCF che desiderano eseguire la migrazione a architetture e piattaforme moderne.
ms.date: 09/02/2019
ms.openlocfilehash: fc93ca4c8f2a28dc4d3a0b0466d19c86273b40b8
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503323"
---
# <a name="why-we-recommend-grpc-for-wcf-developers"></a>Perché è consigliabile gRPC per gli sviluppatori WCF

Prima di approfondire il linguaggio e le tecniche di gRPC, è opportuno illustrare il motivo per cui gRPC è la soluzione ideale per gli sviluppatori di Windows Communication Foundation (WCF) che desiderano eseguire la migrazione a .NET Core.

## <a name="similarity-to-wcf"></a>Somiglianza con WCF

Sebbene l'implementazione e l'approccio siano diversi per gRPC, l'esperienza di sviluppo e utilizzo di servizi con gRPC dovrebbe essere intuitiva per gli sviluppatori WCF. L'obiettivo sottostante è lo stesso: è possibile scrivere codice come se il client e il server si trovino nella stessa piattaforma, senza doversi preoccupare della rete. 

Entrambe le piattaforme condividono il principio di dichiarazione e di implementazione di un'interfaccia, anche se il processo per dichiarare tale interfaccia è diverso. Come si vedrà nel capitolo 5, i diversi tipi di chiamate RPC supportate da gRPC vengono mappati correttamente ai binding disponibili per i servizi WCF.

## <a name="benefits-of-grpc"></a>Vantaggi di gRPC

gRPC si trova al di sopra di altre soluzioni per i motivi seguenti.

### <a name="performance"></a>Prestazioni

L'utilizzo di HTTP/2 anziché HTTP/1.1 rimuove il requisito per i messaggi leggibili e utilizza invece il protocollo binario più piccolo e più veloce. Questa operazione è più efficiente per i computer da analizzare. HTTP/2 supporta inoltre il multiplexing delle richieste su una singola connessione. Questo supporto consente l'invio di risposte non appena si è pronti senza dover attendere in una coda. (In HTTP/1.1 questo problema è noto come "blocco Head-of-line (HOL)". Quando si usa gRPC, è necessario un minor numero di risorse, che lo rende una soluzione efficace da usare per i dispositivi mobili e per le reti più lente.

### <a name="interoperability"></a>Interoperabilità

Sono disponibili strumenti e librerie gRPC per tutti i principali linguaggi di programmazione e piattaforme, tra cui .NET, Java, Python C++, go,, node. js, Swift, Dart, Ruby e php. Grazie al formato di Wire Binary dei buffer del protocollo e alla generazione efficiente del codice per ogni piattaforma, gli sviluppatori possono creare app performanti e usufruire comunque del supporto completo multipiattaforma.

### <a name="usability-and-productivity"></a>Usabilità e produttività

gRPC è una soluzione RPC completa. Funziona in modo coerente in più linguaggi e piattaforme. Fornisce inoltre strumenti eccellenti, con la maggior parte del codice standard necessario generato automaticamente. Più tempo per gli sviluppatori viene liberato per concentrarsi sulla logica di business.

### <a name="streaming"></a>Streaming

gRPC dispone di un flusso bidirezionale completo, che fornisce funzionalità simili ai servizi duplex completi di WCF. il flusso di gRPC può funzionare su connessioni Internet normali, servizi di bilanciamento del carico e mesh dei servizi.

### <a name="deadlinetimeouts-and-cancellation"></a>Scadenza/timeout e annullamento

gRPC consente ai client di specificare il tempo massimo per il completamento di una RPC. Se viene superata la scadenza specificata, il server può annullare l'operazione indipendentemente dal client. Le scadenze e gli annullamenti possono essere propagati tramite ulteriori chiamate gRPC per consentire l'applicazione dei limiti di utilizzo delle risorse. I client possono inoltre arrestare le operazioni quando viene superata una scadenza o prima, se necessario, ad esempio a causa di un'interazione dell'utente.

### <a name="security"></a>Sicurezza

gRPC è protetto in modo implicito quando usa HTTP/2 su una connessione crittografata end-to-end TLS. Il supporto per l'autenticazione del certificato client (vedere il [capitolo 6](security.md)) aumenta ulteriormente la sicurezza e il trust tra client e server.

>[!div class="step-by-step"]
>[Precedente](network-protocols.md)
>[Successivo](protocol-buffers.md)
