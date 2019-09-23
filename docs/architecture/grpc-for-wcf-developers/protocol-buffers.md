---
title: Buffer del protocollo-gRPC per sviluppatori WCF
description: Introduzione al formato wire dei buffer del protocollo usato per la rete gRPC.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 4f9031c86731ea7ded4a812be9967237e52c4b39
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184169"
---
# <a name="protocol-buffers"></a><span data-ttu-id="1dfb7-103">Buffer del protocollo</span><span class="sxs-lookup"><span data-stu-id="1dfb7-103">Protocol buffers</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="1dfb7-104">i servizi gRPC inviano e ricevono dati come *messaggi protobuf (Protocol buffer)* , in modo analogo ai contratti dati di WCF.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to WCF's data contracts.</span></span> <span data-ttu-id="1dfb7-105">Protobuf è un modo efficiente per serializzare i dati strutturati per la lettura e la scrittura dei computer, senza il sovraccarico che i formati leggibili come XML o JSON comportano.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="1dfb7-106">Questo capitolo illustra il funzionamento di protobuf e come definire i propri messaggi protobuf.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="1dfb7-107">Funzionamento di protobuf</span><span class="sxs-lookup"><span data-stu-id="1dfb7-107">How Protobuf works</span></span>

<span data-ttu-id="1dfb7-108">La maggior parte delle tecniche di serializzazione di oggetti .NET, inclusi i contratti dati di WCF, è possibile utilizzare la reflection per analizzare la struttura dell'oggetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at run time.</span></span> <span data-ttu-id="1dfb7-109">Al contrario, la maggior parte delle librerie protobuf richiede di definire la struttura in primo piano usando un linguaggio dedicato (protocollo del buffer `.proto` di*protocollo*) in un file.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-109">By contrast, most Protobuf libraries require you to define the structure up front using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="1dfb7-110">Questo file viene quindi usato da un compilatore per generare il codice per le piattaforme supportate, tra cui .NET, Java, C/C++, JavaScript e molti altri.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-110">This file is then used by a compiler to generate code for any of the supported platforms, including .NET, Java, C/C++, JavaScript, and many more.</span></span> <span data-ttu-id="1dfb7-111">Il compilatore protobuf, `protoc`, è gestito da Google, sebbene siano disponibili implementazioni alternative.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-111">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="1dfb7-112">Il codice generato è efficiente e ottimizzato per la serializzazione e la deserializzazione veloci dei dati.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-112">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="1dfb7-113">Il formato wire protobuf è una codifica binaria, che usa alcuni trucchi intelligenti per ridurre al minimo il numero di byte usati per rappresentare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="1dfb7-113">The Protobuf wire format itself is a binary encoding, which uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="1dfb7-114">La conoscenza del formato di codifica binario non è necessaria per l'uso di protobuf, ma se si è interessati, è possibile ottenere altre informazioni sul [sito Web buffer del protocollo](https://developers.google.com/protocol-buffers/docs/encoding).</span><span class="sxs-lookup"><span data-stu-id="1dfb7-114">Knowledge of the binary encoding format isn't necessary to use Protobuf, but if you're interested you can learn more about it on [the Protocol Buffers web site](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1dfb7-115">[Precedente](why-grpc.md)
>[Successivo](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="1dfb7-115">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
