---
title: Buffer del protocollo-gRPC per sviluppatori WCF
description: Introduzione al formato wire dei buffer del protocollo usato per la rete gRPC.
ms.date: 09/09/2019
ms.openlocfilehash: cc4ff272a9912d6f2dd8f8ddb1972c7369f980fe
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503450"
---
# <a name="protocol-buffers"></a>Buffer del protocollo

i servizi gRPC inviano e ricevono dati come *messaggi protobuf (Protocol buffer)* , in modo analogo ai contratti dati in Windows Communication Foundation (WCF). Protobuf è un modo efficiente per serializzare i dati strutturati per la lettura e la scrittura dei computer, senza il sovraccarico che i formati leggibili come XML o JSON comportano.

Questo capitolo illustra il funzionamento di protobuf e come definire i propri messaggi protobuf.

## <a name="how-protobuf-works"></a>Funzionamento di protobuf

La maggior parte delle tecniche di serializzazione di oggetti .NET, inclusi i contratti dati di WCF, è possibile utilizzare la reflection per analizzare la struttura degli oggetti in fase di esecuzione. Al contrario, la maggior parte delle librerie protobuf richiede di definire la struttura in primo piano usando un linguaggio dedicato (*linguaggio del buffer del protocollo*) in un file di `.proto`. Un compilatore quindi usa questo file per generare il codice per qualsiasi piattaforma supportata. Le piattaforme supportate includono .NET, Java, CC++/, JavaScript e molti altri. 

Il compilatore protobuf, `protoc`, viene gestito da Google, sebbene siano disponibili implementazioni alternative. Il codice generato è efficiente e ottimizzato per la serializzazione e la deserializzazione veloci dei dati.

Il formato wire protobuf è una codifica binaria. USA alcuni trucchi intelligenti per ridurre al minimo il numero di byte usati per rappresentare i messaggi. La conoscenza del formato di codifica binario non è necessaria per l'uso di protobuf. Tuttavia, se si è interessati, è possibile ottenere altre informazioni sul [sito Web buffer del protocollo](https://developers.google.com/protocol-buffers/docs/encoding).

>[!div class="step-by-step"]
>[Precedente](why-grpc.md)
>[Successivo](protobuf-messages.md)
