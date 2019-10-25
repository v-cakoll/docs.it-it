---
title: Confronto tra WCF e gRPC-gRPC per sviluppatori WCF
description: Confronto tra i framework WCF e gRPC per la creazione di applicazioni distribuite.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 5ab1380d4ded52abff08c35c430adf2f3ed7c58b
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846064"
---
# <a name="comparing-wcf-to-grpc"></a>Confronto tra WCF e gRPC

Il capitolo precedente dovrebbe dare un'occhiata a protobuf e al modo in cui gRPC gestisce i messaggi. Prima di eseguire una conversione dettagliata da WCF a gRPC, è importante esaminare il modo in cui la gamma di funzionalità attualmente disponibili in WCF viene gestita in gRPC e le soluzioni alternative che è possibile usare quando non sembra essere un equivalente gRPC. In particolare, in questo capitolo vengono trattati gli argomenti seguenti:

- Operazioni e metodi
- Binding e trasporti
- Tipi RPC
- Metadati
- Gestione degli errori
- Protocolli WS-\*

## <a name="grpc-example"></a>esempio di gRPC

Quando si crea un nuovo progetto ASP.NET Core 3,0 gRPC da Visual Studio 2019 o dalla riga di comando, viene generato automaticamente l'equivalente gRPC di "Hello World". È costituito da un file `greeter.proto` che definisce il servizio e i relativi messaggi e un file `GreeterService.cs` con un'implementazione del servizio.

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

In questo capitolo verrà fatto riferimento a questo codice di esempio per la spiegazione di diversi concetti e funzionalità di gRPC.

>[!div class="step-by-step"]
>[Precedente](protobuf-maps.md)
>[Successivo](wcf-endpoints-grpc-methods.md)
