---
title: Associazioni e trasporti WCF - gRPC per gli sviluppatori WCFWCF bindings and transports - gRPC for WCF developers
description: Informazioni su come le diverse associazioni WCF e trasporti confrontano gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 3a295268b486578c70c2c98f1d05f89070daaeb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147724"
---
# <a name="wcf-bindings-and-transports"></a>Associazioni e trasporti WCF

Windows Communication Foundation (WCF) include *associazioni* predefinite che specificano protocolli di rete, formati di rete e altri dettagli di implementazione diversi. gRPC ha effettivamente un solo protocollo di rete e un formato di filo. (Tecnicamente è *possibile* personalizzare il formato del filo, ma questo non rientra nell'ambito di questo libro.) È probabile scoprire che gRPC offre la soluzione migliore nella maggior parte dei casi.

Quello che segue è una breve discussione sulle associazioni WCF più rilevanti e come si confrontano con i loro equivalenti in gRPC.

## <a name="nettcp"></a>Nettcp

L'associazione NetTCP di WCF consente connessioni permanenti, messaggi di piccole dimensioni e messaggistica bidirezionale. Ma funziona solo tra i client .NET e server. gRPC consente la stessa funzionalità, ma è supportato su più linguaggi di programmazione e piattaforme.

gRPC ha molte funzionalità dell'associazione NetTCP di WCF, ma non sono sempre implementate nello stesso modo. Ad esempio, in WCF, la crittografia viene controllata tramite configurazione e gestita nel framework. In gRPC, la crittografia viene ottenuta a livello di connessione tramite HTTP/2 su TLS.

## <a name="http"></a>HTTP

Il binding WCF denominato BasicHttpBinding è in genere basato su testo e utilizza SOAP come formato di trasmissione. È lento rispetto all'associazione NetTCP. Viene in genere utilizzato per fornire interoperabilità multipiattaforma o connessione tramite l'infrastruttura Internet.It's generally used to provide cross-platform interoperability, or connection over internet infrastructure.

L'equivalente in gRPC utilizza HTTP/2 come livello di trasporto sottostante con il formato wire Protobuf binario per i messaggi. In questo modo può offrire prestazioni a livello di servizio NetTCP e l'interoperabilità cross-platform completa con tutti i linguaggi e i framework di programmazione moderni.

## <a name="named-pipes"></a>Named Pipes

WCF ha fornito un'associazione *di named pipe* per la comunicazione tra processi nello stesso computer fisico. La prima versione di ASP.NET Core gRPC non supporta le named pipe. L'aggiunta del supporto client e server per le named pipe (e i socket di dominio Unix) è un obiettivo per una versione futura.

## <a name="msmq"></a>MSMQ

MSMQ è una coda di messaggi di Windows proprietaria. L'associazione di WCF a MSMQ abilita le richieste "fuoco e dimentica" dai client che potrebbero essere elaborate in qualsiasi momento in futuro. gRPC non fornisce in modo nativo alcuna funzionalità di coda di messaggi.

L'alternativa migliore consiste nell'usare direttamente un sistema di messaggistica come Azure Service Bus, RabbitMQ o Kafka.The best alternative is to directly use a messaging system like Azure Service Bus, RabbitMQ, or Kafka. È possibile implementare questo con il client inserendo i messaggi direttamente nella coda, o un servizio di streaming client gRPC che accoda i messaggi.

## <a name="webhttpbinding"></a>WebHttpBinding

WebHttpBinding (noto anche come `WebGet` REST `WebInvoke` WCF), con gli attributi e, ha consentito di sviluppare API RESTful in grado di parlare JSON in un momento in cui questo era meno comune. Se si dispone di un'API RESTful compilata con WCF REST, è consigliabile eseguirne la migrazione a un'applicazione API Web MVC di ASP.NET base regolare. Questa migrazione fornirebbe la stessa funzionalità di una conversione in gRPC.

>[!div class="step-by-step"]
>[Successivo](wcf-endpoints-grpc-methods.md)
>[precedente](rpc-types.md)
