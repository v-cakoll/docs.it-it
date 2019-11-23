---
title: Binding e trasporti WCF-gRPC per sviluppatori WCF
description: Informazioni sul confronto tra le diverse associazioni e trasporti WCF con gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 233e3d030bc1f4450bd5cd6a7d7770486ca9e95a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966907"
---
# <a name="wcf-bindings-and-transports"></a>Associazioni e trasporti WCF

In WCF sono disponibili numerose *associazioni* predefinite che specificano protocolli di rete, formati di trasmissione e altri dettagli di implementazione diversi. in gRPC è presente un solo protocollo di rete e un formato wire (tecnicamente, il formato wire *può* essere personalizzato, ma questo esula dall'ambito di questo libro). Probabilmente si noterà che gRPC offre la soluzione migliore nella maggior parte dei casi. Di seguito è riportata una breve discussione sulle associazioni WCF più rilevanti e sul modo in cui vengono confrontate con l'equivalente in gRPC.

## <a name="nettcp"></a>NetTCP

Il binding NetTCP di WCF consente connessioni persistenti, messaggi di piccole dimensioni e messaggistica bidirezionale, ma funziona solo tra client e server .NET. gRPC consente la stessa funzionalità ma è supportata in più linguaggi e piattaforme di programmazione. gRPC dispone di molte delle funzionalità dell'associazione WCF NetTCP, sebbene non sempre implementate nello stesso modo. In WCF, ad esempio, la crittografia viene controllata tramite la configurazione e gestita nel Framework. In gRPC, la crittografia viene eseguita a livello di connessione tramite HTTP/2 su TLS.

## <a name="http"></a>HTTP

BasicHttpBinding di WCF è in genere basato su testo, usando SOAP come formato wire ed è lento rispetto all'associazione NetTCP. Viene in genere usato per garantire l'interoperabilità multipiattaforma o la connessione tramite l'infrastruttura Internet. L'equivalente in gRPC, perché usa HTTP/2 come livello di trasporto sottostante con il formato wire protobuf binario per i messaggi, può offrire prestazioni del livello di servizio NetTCP ma con l'interoperabilità multipiattaforma completa con tutti i linguaggi di programmazione moderni e quadri.

## <a name="named-pipes"></a>Named pipe

WCF ha fornito un'associazione named pipes per la comunicazione tra processi nello stesso computer fisico. Le named pipe non sono supportate dalla prima versione di ASP.NET Core gRPC. L'aggiunta del supporto client e server per le named pipe e i socket di dominio UNIX è un obiettivo di una versione futura.

## <a name="msmq"></a>MSMQ

MSMQ è una coda di messaggi di Windows proprietaria. Il binding di WCF a MSMQ consente di attivare e dimenticare richieste da client che possono essere elaborati in qualsiasi momento in futuro. gRPC non fornisce in modo nativo alcuna funzionalità della coda di messaggi. L'alternativa migliore consiste nell'usare direttamente un sistema di messaggistica come il bus di servizio di Azure, RabbitMQ o Kafka. Questa operazione può essere implementata con il client che inserisce messaggi direttamente nella coda o un servizio di streaming client gRPC che accoda i messaggi.

## <a name="webhttpbinding"></a>WebHttpBinding

WebHttpBinding (noto anche come WCF ReST), con gli attributi `WebGet` e `WebInvoke`, consente di sviluppare API ReSTful che possono pronunciare JSON alla volta quando questo era meno comune di adesso. Pertanto, se si dispone di un'API RESTful compilata con WCF REST, provare a eseguire la migrazione a una normale applicazione API Web MVC ASP.NET Core, che fornisce funzionalità equivalenti, anziché eseguire la conversione in gRPC.

>[!div class="step-by-step"]
>[Precedente](wcf-endpoints-grpc-methods.md)
>[Successivo](rpc-types.md)
