---
title: Confronto tra WCF e gRPC-gRPC per sviluppatori WCF
description: Confronto tra i framework WCF e gRPC per la creazione di applicazioni distribuite.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: c763048d09e7ed5ca0a3d5240f6b3cf5262f897c
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184043"
---
# <a name="comparing-wcf-to-grpc"></a><span data-ttu-id="c36b0-103">Confronto tra WCF e gRPC</span><span class="sxs-lookup"><span data-stu-id="c36b0-103">Comparing WCF to gRPC</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="c36b0-104">Il capitolo precedente dovrebbe dare un'occhiata a protobuf e al modo in cui gRPC gestisce i messaggi.</span><span class="sxs-lookup"><span data-stu-id="c36b0-104">The previous chapter should have given you a good look at Protobuf and how gRPC handles messages.</span></span> <span data-ttu-id="c36b0-105">Prima di eseguire una conversione dettagliata da WCF a gRPC, è importante esaminare il modo in cui la gamma di funzionalità attualmente disponibili in WCF viene gestita in gRPC e le soluzioni alternative che è possibile usare quando non sembra essere un equivalente gRPC.</span><span class="sxs-lookup"><span data-stu-id="c36b0-105">Before working through a detailed conversion from WCF to gRPC, it's important to look at how the range of features currently available in WCF are handled in gRPC and what workarounds you can use when there doesn't appear to be a gRPC equivalent.</span></span> <span data-ttu-id="c36b0-106">In particolare, in questo capitolo vengono trattati gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c36b0-106">In particular, this chapter will cover the following subjects:</span></span>

- <span data-ttu-id="c36b0-107">Operazioni e metodi</span><span class="sxs-lookup"><span data-stu-id="c36b0-107">Operations and methods</span></span>
- <span data-ttu-id="c36b0-108">Binding e trasporti</span><span class="sxs-lookup"><span data-stu-id="c36b0-108">Bindings and transports</span></span>
- <span data-ttu-id="c36b0-109">Tipi RPC</span><span class="sxs-lookup"><span data-stu-id="c36b0-109">RPC types</span></span>
- <span data-ttu-id="c36b0-110">Metadati</span><span class="sxs-lookup"><span data-stu-id="c36b0-110">Metadata</span></span>
- <span data-ttu-id="c36b0-111">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="c36b0-111">Error handling</span></span>
- <span data-ttu-id="c36b0-112">\* Protocolli WS</span><span class="sxs-lookup"><span data-stu-id="c36b0-112">WS-\* protocols</span></span>

## <a name="grpc-example"></a><span data-ttu-id="c36b0-113">esempio di gRPC</span><span class="sxs-lookup"><span data-stu-id="c36b0-113">gRPC example</span></span>

<span data-ttu-id="c36b0-114">Quando si crea un nuovo progetto ASP.NET Core 3,0 gRPC da Visual Studio 2019 o dalla riga di comando, viene generato automaticamente l'equivalente gRPC di "Hello World".</span><span class="sxs-lookup"><span data-stu-id="c36b0-114">When you create a new ASP.NET Core 3.0 gRPC project from Visual Studio 2019 or the command line, the gRPC equivalent of "Hello World" is generated for you.</span></span> <span data-ttu-id="c36b0-115">È costituito da `greeter.proto` un file che definisce il servizio e i relativi messaggi e `GreeterService.cs` un file con un'implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="c36b0-115">It consists of a `greeter.proto` file that defines the service and its messages, and a `GreeterService.cs` file with an implementation of the service.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "HelloGrpc";

package Greet;

// The greeting service definition.
service Greeter {
  // Sends a greeting
  rpc SayHello (HelloRequest) returns (HelloReply);
}

// The request message containing the user's name.
message HelloRequest {
  string name = 1;
}

// The response message containing the greetings.
message HelloReply {
  string message = 1;
}
```

```csharp
using System.Threading.Tasks;
using Grpc.Core;
using Microsoft.Extensions.Logging;

namespace HelloGrpc
{
    public class GreeterService : Greeter.GreeterBase
    {
        private readonly ILogger<GreeterService> _logger;
        public GreeterService(ILogger<GreeterService> logger)
        {
            _logger = logger;
        }

        public override Task<HelloReply> SayHello(HelloRequest request, ServerCallContext context)
        {
            return Task.FromResult(new HelloReply
            {
                Message = "Hello " + request.Name
            });
        }
    }
}
```

<span data-ttu-id="c36b0-116">In questo capitolo verrà fatto riferimento a questo codice di esempio per la spiegazione di diversi concetti e funzionalità di gRPC.</span><span class="sxs-lookup"><span data-stu-id="c36b0-116">This chapter will refer to this example code when explaining various concepts and features of gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c36b0-117">[Precedente](protobuf-maps.md)
>[Successivo](wcf-endpoints-grpc-methods.md)</span><span class="sxs-lookup"><span data-stu-id="c36b0-117">[Previous](protobuf-maps.md)
[Next](wcf-endpoints-grpc-methods.md)</span></span>
