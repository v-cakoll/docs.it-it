---
title: Buffer di protocollo - gRPC per gli sviluppatori WCFProtocol Buffers - gRPC for WCF developers
description: Introduzione al formato wire dei buffer di protocollo utilizzato per la rete gRPC.
ms.date: 09/09/2019
ms.openlocfilehash: 35319d299a8bc2866a87954b3e54bfda9314ffe8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147932"
---
# <a name="protocol-buffers"></a>Buffer di protocollo

I servizi gRPC inviano e ricevono dati come messaggi di buffer di *protocollo (Protobuf),* in modo simile ai contratti dati in Windows Communication Foundation (WCF). Protobuf è un modo efficiente di serializzare i dati strutturati per le macchine per la lettura e la scrittura, senza l'overhead che i formati leggibili come XML o JSON comportano.

Questo capitolo descrive come funziona Protobuf e come definire i tuoi messaggi Protobuf.

## <a name="how-protobuf-works"></a>Come funziona Protobuf

La maggior parte delle tecniche di serializzazione degli oggetti .NET, inclusi i contratti dati di WCF, funzionano utilizzando la reflection per analizzare la struttura dell'oggetto in fase di esecuzione. Al contrario, la maggior parte delle librerie Protobuf richiedono di definire la `.proto` struttura in anticipo utilizzando un linguaggio dedicato ( Protocol Buffer*Language*) in un file. Un compilatore utilizza quindi questo file per generare codice per una qualsiasi delle piattaforme supportate. Le piattaforme supportate includono .NET, Java, C/C, JavaScript e molti altri.

Il compilatore Protobuf, `protoc`, è gestito da Google, anche se sono disponibili implementazioni alternative. Il codice generato è efficiente e ottimizzato per la serializzazione e la deserializzazione rapida dei dati.

Il formato di filo Protobuf è una codifica binaria. Esso utilizza alcuni trucchi intelligenti per ridurre al minimo il numero di byte utilizzati per rappresentare i messaggi. La conoscenza del formato di codifica binaria non è necessaria per utilizzare Protobuf. Ma se siete interessati, si può imparare di più su di esso [sul sito Web Protocol Buffers](https://developers.google.com/protocol-buffers/docs/encoding).

>[!div class="step-by-step"]
>[Successivo](why-grpc.md)
>[precedente](protobuf-messages.md)
