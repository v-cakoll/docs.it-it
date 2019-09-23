---
title: Binding e trasporti WCF-gRPC per sviluppatori WCF
description: Informazioni sul confronto tra le diverse associazioni e trasporti WCF con gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 50bac73ee68d7156fc5fed55dfffb3ba7f2de924
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184057"
---
# <a name="wcf-bindings-and-transports"></a>Associazioni e trasporti WCF

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

In WCF sono disponibili numerose *associazioni* predefinite che specificano protocolli di rete, formati di trasmissione e altri dettagli di implementazione diversi. in gRPC è presente un solo protocollo di rete e un formato wire (tecnicamente, il formato wire *può* essere personalizzato, ma questo esula dall'ambito di questo libro). Probabilmente si noterà che gRPC offre la soluzione migliore nella maggior parte dei casi. Di seguito è riportata una breve discussione sulle associazioni WCF più rilevanti e sul modo in cui vengono confrontate con l'equivalente in gRPC.

## <a name="nettcp"></a>NetTCP

Il binding NetTCP di WCF consente connessioni persistenti, messaggi di piccole dimensioni e messaggistica bidirezionale, ma funziona solo tra client e server .NET. gRPC consente la stessa funzionalità ma è supportata in più linguaggi e piattaforme di programmazione. gRPC dispone di molte delle funzionalità dell'associazione WCF NetTCP, sebbene non sempre implementate nello stesso modo. In WCF, ad esempio, la crittografia viene controllata tramite la configurazione e gestita nel Framework. In gRPC, la crittografia viene eseguita a livello di connessione tramite HTTP/2 su TLS.

## <a name="http"></a>HTTP

BasicHttpBinding di WCF è in genere basato su testo, usando SOAP come formato wire ed è molto lento dagli standard delle applicazioni di rete moderne. Viene usato solo per fornire l'interoperabilità multipiattaforma o la connessione tramite l'infrastruttura Internet. L'equivalente in gRPC, perché usa HTTP/2 come livello di trasporto sottostante con il formato wire protobuf binario per i messaggi, può offrire prestazioni del livello di servizio NetTCP ma con l'interoperabilità multipiattaforma completa con tutti i linguaggi di programmazione moderni e quadri.

## <a name="named-pipes"></a>Named pipe

WCF ha fornito un'associazione named pipes per la comunicazione tra processi nello stesso computer fisico. Le named pipe non sono supportate dalla prima versione di ASP.NET Core gRPC.

All'esterno di Windows, la funzionalità fornita dalle named pipe viene invece fornita in genere dai socket di dominio UNIX. Questi socket sono socket di tipo TCP regolari rappresentati con indirizzi di file System, ad `/var/run/docker.sock`esempio, che gRPC può funzionare sia come client che come server. Se è necessario usare la funzionalità di stile Named Pipes in Windows, il prossimo aggiornamento a Windows 10 e Windows Server, in 2019 Q4, aggiunge i socket di dominio come funzionalità nativa completamente supportata all'interno di Windows. Quindi, i servizi gRPC in esecuzione in queste e versioni successive di Windows (o in Linux) possono usare i socket di dominio anziché le named pipe. Tuttavia, se il team non è in grado di eseguire l'aggiornamento alla versione più recente di Windows, sarà necessario usare i socket TCP localhost. I problemi di sicurezza relativi all'uso di socket TCP locali possono essere risolti con l'uso dell'autenticazione del certificato tra client e server.

## <a name="msmq"></a>MSMQ

MSMQ è una coda di messaggi di Windows proprietaria. Il binding di WCF a MSMQ consente di attivare e dimenticare richieste da client che possono essere elaborati in qualsiasi momento in futuro. gRPC non fornisce in modo nativo alcuna funzionalità della coda di messaggi. L'alternativa migliore consiste nell'usare direttamente un sistema di messaggistica come il bus di servizio di Azure, RabbitMQ o Kafka. Questa operazione può essere implementata con il client che inserisce messaggi direttamente nella coda o un servizio di streaming client gRPC che accoda i messaggi.

## <a name="webhttpbinding"></a>WebHttpBinding

WebHttpBinding (noto anche come WCF REST), con gli `WebGet` attributi e `WebInvoke` , consente di sviluppare API RESTful che possono pronunciare JSON in un momento in cui questa situazione era meno comune di ora. Pertanto, se si dispone di un'API RESTful compilata con WCF REST, provare a eseguire la migrazione a una normale applicazione API Web MVC ASP.NET Core, che fornisce funzionalità equivalenti, anziché eseguire la conversione in gRPC.

>[!div class="step-by-step"]
>[Precedente](wcf-endpoints-grpc-methods.md)
>[Successivo](rpc-types.md)
