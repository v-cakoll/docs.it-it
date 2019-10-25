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
# <a name="protocol-buffers"></a><span data-ttu-id="84bf8-103">Buffer del protocollo</span><span class="sxs-lookup"><span data-stu-id="84bf8-103">Protocol buffers</span></span>

<span data-ttu-id="84bf8-104">i servizi gRPC inviano e ricevono dati come *messaggi protobuf (Protocol buffer)* , in modo analogo ai contratti dati di WCF.</span><span class="sxs-lookup"><span data-stu-id="84bf8-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to WCF's data contracts.</span></span> <span data-ttu-id="84bf8-105">Protobuf è un modo efficiente per serializzare i dati strutturati per la lettura e la scrittura dei computer, senza il sovraccarico che i formati leggibili come XML o JSON comportano.</span><span class="sxs-lookup"><span data-stu-id="84bf8-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="84bf8-106">Questo capitolo illustra il funzionamento di protobuf e come definire i propri messaggi protobuf.</span><span class="sxs-lookup"><span data-stu-id="84bf8-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="84bf8-107">Funzionamento di protobuf</span><span class="sxs-lookup"><span data-stu-id="84bf8-107">How Protobuf works</span></span>

<span data-ttu-id="84bf8-108">La maggior parte delle tecniche di serializzazione di oggetti .NET, inclusi i contratti dati di WCF, è possibile utilizzare la reflection per analizzare la struttura dell'oggetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="84bf8-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at run time.</span></span> <span data-ttu-id="84bf8-109">Al contrario, la maggior parte delle librerie protobuf richiede di definire la struttura in primo piano usando un linguaggio dedicato (*protocollo di buffer del protocollo*) in un file di `.proto`.</span><span class="sxs-lookup"><span data-stu-id="84bf8-109">By contrast, most Protobuf libraries require you to define the structure up front using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="84bf8-110">Questo file viene quindi usato da un compilatore per generare il codice per le piattaforme supportate, tra cui .NET, Java, C/C++, JavaScript e molti altri.</span><span class="sxs-lookup"><span data-stu-id="84bf8-110">This file is then used by a compiler to generate code for any of the supported platforms, including .NET, Java, C/C++, JavaScript, and many more.</span></span> <span data-ttu-id="84bf8-111">Il compilatore protobuf, `protoc`, viene gestito da Google, sebbene siano disponibili implementazioni alternative.</span><span class="sxs-lookup"><span data-stu-id="84bf8-111">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="84bf8-112">Il codice generato è efficiente e ottimizzato per la serializzazione e la deserializzazione veloci dei dati.</span><span class="sxs-lookup"><span data-stu-id="84bf8-112">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="84bf8-113">Il formato wire protobuf è una codifica binaria, che usa alcuni trucchi intelligenti per ridurre al minimo il numero di byte usati per rappresentare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="84bf8-113">The Protobuf wire format itself is a binary encoding, which uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="84bf8-114">La conoscenza del formato di codifica binario non è necessaria per l'uso di protobuf, ma se si è interessati, è possibile ottenere altre informazioni sul [sito Web buffer del protocollo](https://developers.google.com/protocol-buffers/docs/encoding).</span><span class="sxs-lookup"><span data-stu-id="84bf8-114">Knowledge of the binary encoding format isn't necessary to use Protobuf, but if you're interested you can learn more about it on [the Protocol Buffers web site](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="84bf8-115">[Precedente](why-grpc.md)
>[Successivo](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="84bf8-115">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
