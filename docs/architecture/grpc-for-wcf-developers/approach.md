---
title: Modalità di gRPC approcci RPC-gRPC per gli sviluppatori WCF
description: Confronto tra le funzionalità principali di WCF e gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: b924d2f20b54de2d6476a0b27626d5dd7fd0986f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711485"
---
# <a name="how-grpc-approaches-rpc"></a>Approccio di gRPC per RPC

Windows Communication Foundation (WCF) e gRPC sono entrambe implementazioni del modello RPC ( *Remote Procedure Call* ). Questo modello mira a effettuare chiamate ai servizi eseguiti in un computer diverso o in un processo diverso, che funzionano in modo uniforme, come le chiamate al metodo nell'applicazione client. Sebbene gli obiettivi di WCF e gRPC siano gli stessi, i dettagli dell'implementazione sono piuttosto diversi.

La tabella seguente illustra il modo in cui le funzionalità principali di WCF sono correlate a gRPC e in cui è possibile trovare spiegazioni più dettagliate.

| Funzionalità | WCF | gRPC |
| -------- | --- | ---- |
| Obiettivo | Separare il codice business dall'implementazione di rete. | Codice business separato dalla definizione dell'interfaccia e dall'implementazione di rete. |
| Definire i servizi e i messaggi (capitoli 3-4)  | Contratto di servizio, contratto dell'operazione e contratto dati. | Usa il file proto per dichiarare servizi e messaggi. |
| Lingua (capitoli 3-5) | Contratti scritti in C# o Visual Basic. | Lingua del buffer del protocollo. |
| Formato wire (capitolo 3) | Configurabile, tra cui SOAP/XML, plain XML, JSON e .NET Binary. | Formato binario del buffer del protocollo (anche se è possibile usare altri formati).
| Interoperabilità (capitolo 4) | Quando si usa SOAP su HTTP. | Supporto ufficiale: .NET, Java, Python, JavaScript, C/C++, go, Rust, Ruby, Swift, Dart, php. Supporto non ufficiale per altre lingue della community. |
| Rete (capitolo 4) | Configurato in fase di esecuzione. Passare da NetTCP, HTTP e MSMQ. | HTTP/2, attualmente su TCP solo con ASP.NET Core gRPC. |
| Approccio (capitolo 4) | Generazione di runtime di serializzazione, deserializzazione e codice di rete nelle classi di base. | Generazione in fase di compilazione di serializzazione, deserializzazione e codice di rete nelle classi di base. |
| Sicurezza (capitolo 6) | Autenticazione, WS-Security, crittografia messaggi. | Credenziali, sicurezza ASP.NET Core, rete TLS. |

>[!div class="step-by-step"]
>[Precedente](grpc-overview.md)
>[Successivo](interface-definition-language.md)
