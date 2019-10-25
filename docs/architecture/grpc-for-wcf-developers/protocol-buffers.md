---
title: Buffer del protocollo-gRPC per sviluppatori WCF
description: Introduzione al formato wire dei buffer del protocollo usato per la rete gRPC.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 6b47c7f3576134d8ee44f79e329cc4879661e6c3
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846307"
---
# <a name="protocol-buffers"></a>Buffer del protocollo

i servizi gRPC inviano e ricevono dati come *messaggi protobuf (Protocol buffer)* , in modo analogo ai contratti dati di WCF. Protobuf è un modo efficiente per serializzare i dati strutturati per la lettura e la scrittura dei computer, senza il sovraccarico che i formati leggibili come XML o JSON comportano.

Questo capitolo illustra il funzionamento di protobuf e come definire i propri messaggi protobuf.

## <a name="how-protobuf-works"></a>Funzionamento di protobuf

La maggior parte delle tecniche di serializzazione di oggetti .NET, inclusi i contratti dati di WCF, è possibile utilizzare la reflection per analizzare la struttura dell'oggetto in fase di esecuzione. Al contrario, la maggior parte delle librerie protobuf richiede di definire la struttura in primo piano usando un linguaggio dedicato (*protocollo di buffer del protocollo*) in un file di `.proto`. Questo file viene quindi usato da un compilatore per generare il codice per le piattaforme supportate, tra cui .NET, Java, C/C++, JavaScript e molti altri. Il compilatore protobuf, `protoc`, viene gestito da Google, sebbene siano disponibili implementazioni alternative. Il codice generato è efficiente e ottimizzato per la serializzazione e la deserializzazione veloci dei dati.

Il formato wire protobuf è una codifica binaria, che usa alcuni trucchi intelligenti per ridurre al minimo il numero di byte usati per rappresentare i messaggi. La conoscenza del formato di codifica binario non è necessaria per l'uso di protobuf, ma se si è interessati, è possibile ottenere altre informazioni sul [sito Web buffer del protocollo](https://developers.google.com/protocol-buffers/docs/encoding).

>[!div class="step-by-step"]
>[Precedente](why-grpc.md)
>[Successivo](protobuf-messages.md)
