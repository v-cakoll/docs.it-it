---
title: Confronto tra WCF e gRPC-gRPC per sviluppatori WCF
description: Confronto tra i framework WCF e gRPC per la creazione di applicazioni distribuite.
ms.date: 09/02/2019
ms.openlocfilehash: 4f54db76c9512b770b4dd993496d95437dd89753
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503342"
---
# <a name="comparing-wcf-to-grpc"></a>Confronto tra WCF e gRPC

Il capitolo precedente ha dato una migliore occhiata a protobuf e al modo in cui gRPC gestisce i messaggi. Prima di eseguire una conversione dettagliata da Windows Communication Foundation (WCF) a gRPC, è importante sapere in che modo le funzionalità disponibili in WCF vengono gestite in gRPC e quali soluzioni alternative è possibile utilizzare quando non è presente alcun equivalente gRPC. In particolare, in questo capitolo vengono trattati gli argomenti seguenti:

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

// The request message that contains the user's name.
message HelloRequest {
  string name = 1;
}

// The response message that contains the greetings.
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

In questo capitolo verrà fatto riferimento a questo codice di esempio per la spiegazione di concetti e funzionalità diversi di gRPC.

>[!div class="step-by-step"]
>[Precedente](protobuf-maps.md)
>[Successivo](wcf-endpoints-grpc-methods.md)
