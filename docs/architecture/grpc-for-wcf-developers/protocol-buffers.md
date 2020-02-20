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
# <a name="protocol-buffers"></a><span data-ttu-id="a843c-103">Buffer del protocollo</span><span class="sxs-lookup"><span data-stu-id="a843c-103">Protocol buffers</span></span>

<span data-ttu-id="a843c-104">i servizi gRPC inviano e ricevono dati come *messaggi protobuf (Protocol buffer)* , in modo analogo ai contratti dati in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a843c-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to data contracts in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="a843c-105">Protobuf è un modo efficiente per serializzare i dati strutturati per la lettura e la scrittura dei computer, senza il sovraccarico che i formati leggibili come XML o JSON comportano.</span><span class="sxs-lookup"><span data-stu-id="a843c-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="a843c-106">Questo capitolo illustra il funzionamento di protobuf e come definire i propri messaggi protobuf.</span><span class="sxs-lookup"><span data-stu-id="a843c-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="a843c-107">Funzionamento di protobuf</span><span class="sxs-lookup"><span data-stu-id="a843c-107">How Protobuf works</span></span>

<span data-ttu-id="a843c-108">La maggior parte delle tecniche di serializzazione di oggetti .NET, inclusi i contratti dati di WCF, è possibile utilizzare la reflection per analizzare la struttura degli oggetti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a843c-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at runtime.</span></span> <span data-ttu-id="a843c-109">Al contrario, la maggior parte delle librerie protobuf richiede di definire la struttura in primo piano usando un linguaggio dedicato (*linguaggio del buffer del protocollo*) in un file di `.proto`.</span><span class="sxs-lookup"><span data-stu-id="a843c-109">By contrast, most Protobuf libraries require you to define the structure up front by using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="a843c-110">Un compilatore quindi usa questo file per generare il codice per qualsiasi piattaforma supportata.</span><span class="sxs-lookup"><span data-stu-id="a843c-110">A compiler then uses this file to generate code for any of the supported platforms.</span></span> <span data-ttu-id="a843c-111">Le piattaforme supportate includono .NET, Java, CC++/, JavaScript e molti altri.</span><span class="sxs-lookup"><span data-stu-id="a843c-111">Supported platforms include .NET, Java, C/C++, JavaScript, and many more.</span></span> 

<span data-ttu-id="a843c-112">Il compilatore protobuf, `protoc`, viene gestito da Google, sebbene siano disponibili implementazioni alternative.</span><span class="sxs-lookup"><span data-stu-id="a843c-112">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="a843c-113">Il codice generato è efficiente e ottimizzato per la serializzazione e la deserializzazione veloci dei dati.</span><span class="sxs-lookup"><span data-stu-id="a843c-113">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="a843c-114">Il formato wire protobuf è una codifica binaria.</span><span class="sxs-lookup"><span data-stu-id="a843c-114">The Protobuf wire format is a binary encoding.</span></span> <span data-ttu-id="a843c-115">USA alcuni trucchi intelligenti per ridurre al minimo il numero di byte usati per rappresentare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="a843c-115">It uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="a843c-116">La conoscenza del formato di codifica binario non è necessaria per l'uso di protobuf.</span><span class="sxs-lookup"><span data-stu-id="a843c-116">Knowledge of the binary encoding format isn't necessary to use Protobuf.</span></span> <span data-ttu-id="a843c-117">Tuttavia, se si è interessati, è possibile ottenere altre informazioni sul [sito Web buffer del protocollo](https://developers.google.com/protocol-buffers/docs/encoding).</span><span class="sxs-lookup"><span data-stu-id="a843c-117">But if you're interested, you can learn more about it on [the Protocol Buffers website](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a843c-118">[Precedente](why-grpc.md)
>[Successivo](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="a843c-118">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
