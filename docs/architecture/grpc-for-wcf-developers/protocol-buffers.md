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
# <a name="protocol-buffers"></a><span data-ttu-id="f60a4-103">Buffer di protocollo</span><span class="sxs-lookup"><span data-stu-id="f60a4-103">Protocol buffers</span></span>

<span data-ttu-id="f60a4-104">I servizi gRPC inviano e ricevono dati come messaggi di buffer di *protocollo (Protobuf),* in modo simile ai contratti dati in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f60a4-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to data contracts in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="f60a4-105">Protobuf è un modo efficiente di serializzare i dati strutturati per le macchine per la lettura e la scrittura, senza l'overhead che i formati leggibili come XML o JSON comportano.</span><span class="sxs-lookup"><span data-stu-id="f60a4-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="f60a4-106">Questo capitolo descrive come funziona Protobuf e come definire i tuoi messaggi Protobuf.</span><span class="sxs-lookup"><span data-stu-id="f60a4-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="f60a4-107">Come funziona Protobuf</span><span class="sxs-lookup"><span data-stu-id="f60a4-107">How Protobuf works</span></span>

<span data-ttu-id="f60a4-108">La maggior parte delle tecniche di serializzazione degli oggetti .NET, inclusi i contratti dati di WCF, funzionano utilizzando la reflection per analizzare la struttura dell'oggetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f60a4-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at runtime.</span></span> <span data-ttu-id="f60a4-109">Al contrario, la maggior parte delle librerie Protobuf richiedono di definire la `.proto` struttura in anticipo utilizzando un linguaggio dedicato ( Protocol Buffer*Language*) in un file.</span><span class="sxs-lookup"><span data-stu-id="f60a4-109">By contrast, most Protobuf libraries require you to define the structure up front by using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="f60a4-110">Un compilatore utilizza quindi questo file per generare codice per una qualsiasi delle piattaforme supportate.</span><span class="sxs-lookup"><span data-stu-id="f60a4-110">A compiler then uses this file to generate code for any of the supported platforms.</span></span> <span data-ttu-id="f60a4-111">Le piattaforme supportate includono .NET, Java, C/C, JavaScript e molti altri.</span><span class="sxs-lookup"><span data-stu-id="f60a4-111">Supported platforms include .NET, Java, C/C++, JavaScript, and many more.</span></span>

<span data-ttu-id="f60a4-112">Il compilatore Protobuf, `protoc`, è gestito da Google, anche se sono disponibili implementazioni alternative.</span><span class="sxs-lookup"><span data-stu-id="f60a4-112">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="f60a4-113">Il codice generato è efficiente e ottimizzato per la serializzazione e la deserializzazione rapida dei dati.</span><span class="sxs-lookup"><span data-stu-id="f60a4-113">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="f60a4-114">Il formato di filo Protobuf è una codifica binaria.</span><span class="sxs-lookup"><span data-stu-id="f60a4-114">The Protobuf wire format is a binary encoding.</span></span> <span data-ttu-id="f60a4-115">Esso utilizza alcuni trucchi intelligenti per ridurre al minimo il numero di byte utilizzati per rappresentare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="f60a4-115">It uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="f60a4-116">La conoscenza del formato di codifica binaria non è necessaria per utilizzare Protobuf.</span><span class="sxs-lookup"><span data-stu-id="f60a4-116">Knowledge of the binary encoding format isn't necessary to use Protobuf.</span></span> <span data-ttu-id="f60a4-117">Ma se siete interessati, si può imparare di più su di esso [sul sito Web Protocol Buffers](https://developers.google.com/protocol-buffers/docs/encoding).</span><span class="sxs-lookup"><span data-stu-id="f60a4-117">But if you're interested, you can learn more about it on [the Protocol Buffers website](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f60a4-118">[Successivo](why-grpc.md)
>[precedente](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="f60a4-118">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
