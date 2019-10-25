---
title: Modalità di gRPC approcci RPC-gRPC per gli sviluppatori WCF
description: Confronto tra le funzionalità principali di WCF e gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 3da28968f8c8bd6c4fdba7432ffc8458d8340457
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846692"
---
# <a name="how-grpc-approaches-rpc"></a>Approccio di gRPC per RPC

Windows Communication Foundation (WCF) e gRPC sono entrambe implementazioni del modello RPC ( *Remote Procedure Call* ), che mira a eseguire chiamate ai servizi in esecuzione in un computer diverso o in un processo diverso, come se fossero semplicemente chiamate al metodo nell'applicazione client. Sebbene gli obiettivi di WCF e gRPC siano gli stessi, i dettagli dell'implementazione sono piuttosto diversi.

La tabella seguente illustra il modo in cui le funzionalità principali di WCF sono correlate a gRPC e in cui è possibile trovare spiegazioni più dettagliate nel resto del libro.

| Funzionalità | WCF | gRPC |
| -------- | --- | ---- |
| Obiettivo | Separare il codice aziendale dall'implementazione della rete | Separare il codice aziendale dalla definizione dell'interfaccia e dall'implementazione della rete |
| Definire servizi e messaggi (capitolo 3-4)  | Contratto di servizio, contratto dell'operazione e contratto dati | Usa il file proto per dichiarare servizi e messaggi |
| Lingua (capitolo 3-5) | Contratti scritti in C# o Visual Basic | Lingua del buffer del protocollo |
| Formato wire (capitolo 3) | Configurabile, tra cui SOAP/XML, plain XML, JSON, .NET Binary e così via. | Formato binario del buffer del protocollo (anche se è possibile usare altri formati).
| Interoperabilità (capitolo 4) | Quando si usa SOAP su HTTP | Supporto ufficiale: .NET, Java, Python, JavaScript, C/C++, go, Rust, Ruby, Swift, Dart, php. Supporto non ufficiale per altre lingue della community. |
| Rete (capitolo 4) | Configurato in fase di esecuzione. Passare da NetTCP, HTTP, MSMQ e così via. | HTTP/2, attualmente su TCP solo con ASP.NET Core gRPC. |
| Approccio (capitolo 4) | Generazione di runtime di/deserialization di serializzazione e codice di rete nelle classi base | Generazione in fase di compilazione di/deserialization di serializzazione e codice di rete nelle classi di base |
| Sicurezza (capitolo 6) | Autenticazione, WS-Security, crittografia messaggi | Credenziali, sicurezza ASP.NET Core, rete TLS |

>[!div class="step-by-step"]
>[Precedente](grpc-overview.md)
>[Successivo](interface-definition-language.md)
