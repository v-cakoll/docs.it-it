---
title: Perché gRPC è consigliato per gli sviluppatori WCF-gRPC per sviluppatori WCF
description: Descrizione del motivo per cui gRPC è una soluzione ideale per gli sviluppatori WCF che desiderano eseguire la migrazione a architetture e piattaforme moderne.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: f96e9a059dc9f12a13c9eb5bb7184ee75d602458
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846075"
---
# <a name="why-grpc-is-recommended-for-wcf-developers"></a>Perché gRPC è consigliato per gli sviluppatori WCF

Prima di approfondire il linguaggio e le tecniche di gRPC, è opportuno illustrare il motivo per cui gRPC è la soluzione ideale per gli sviluppatori WCF che vogliono eseguire la migrazione a .NET Core, dato che sono disponibili alternative.

## <a name="similarity-to-wcf"></a>Somiglianza con WCF

Sebbene l'implementazione e l'approccio siano diversi, l'esperienza effettiva di sviluppo e utilizzo di servizi con gRPC dovrebbe essere molto intuitiva per gli sviluppatori di WCF. L'obiettivo principale di rendere possibile il codice come se il client e il server si trovassero nella stessa piattaforma, senza doversi preoccupare della rete, è lo stesso. Entrambe le piattaforme condividono il principio di dichiarazione e di implementazione di un'interfaccia, anche se il processo per dichiarare tale interfaccia è diverso. Come si vedrà nel capitolo 5, i diversi tipi di chiamate RPC supportati da gRPC vengono mappati in modo ottimale ai diversi binding disponibili per i servizi WCF.

## <a name="benefits-of-grpc"></a>Vantaggi di gRPC

Ulteriori motivi per cui gRPC si trova al di sopra di altre soluzioni sono:

### <a name="performance"></a>Prestazioni

Come già illustrato, l'uso di HTTP/2 anziché HTTP/1.1 rimuove il requisito per i messaggi leggibili e usa invece il protocollo binario più veloce. Questa operazione è più efficiente per i computer da analizzare. HTTP/2 supporta anche le richieste di multiplexing su una singola connessione, consentendo l'invio di risposte non appena sono pronte senza dover attendere in una coda (un problema in HTTP/1.1 noto come "blocco di intestazioni di riga (HOL)"). Quando si usa gRPC è necessario un minor numero di risorse, che lo rende una soluzione efficace da usare per i dispositivi mobili e per le reti più lente.

### <a name="interoperability"></a>Interoperabilità

Sono disponibili strumenti e librerie gRPC per tutti i principali linguaggi di programmazione e piattaforme, tra cui .NET, Java, Python C++, go,, node. js, Swift, Dart, Ruby e php. Grazie al formato di Wire Binary dei buffer del protocollo e alla generazione efficiente del codice per ogni piattaforma, gli sviluppatori possono creare app performanti e usufruire comunque del supporto completo multipiattaforma.

### <a name="usability-and-productivity"></a>Usabilità e produttività

gRPC è una soluzione RPC completa. Funziona in modo coerente in più linguaggi e piattaforme e fornisce strumenti eccellenti, con la maggior parte del codice standard necessario generato automaticamente, quindi è possibile liberare più tempo per gli sviluppatori per concentrarsi sulla logica di business.

### <a name="streaming"></a>Flusso

gRPC dispone di un flusso bidirezionale completo che fornisce funzionalità molto simili ai servizi duplex completi di WCF. il flusso di gRPC può funzionare su connessioni Internet normali, servizi di bilanciamento del carico e mesh dei servizi.

### <a name="deadlinetimeouts-and-cancellation"></a>Scadenza/timeout e annullamento

gRPC consente ai client di specificare il tempo massimo per il completamento di una RPC. Se viene superata la scadenza specificata, il server può annullare l'operazione indipendentemente dal client. Le scadenze e gli annullamenti possono essere propagati tramite ulteriori chiamate gRPC per consentire l'applicazione dei limiti di utilizzo delle risorse. I client possono anche interrompere le operazioni quando viene superata una scadenza o prima, se necessario, ad esempio a causa di un'interazione dell'utente.

### <a name="security"></a>Sicurezza

gRPC è protetto in modo implicito quando si usa HTTP/2 su una connessione crittografata end-to-end TLS. Il supporto per l'autenticazione del certificato client (vedere il capitolo 6) aumenta ulteriormente la sicurezza e il trust tra client e server.

>[!div class="step-by-step"]
>[Precedente](network-protocols.md)
>[Successivo](protocol-buffers.md)
