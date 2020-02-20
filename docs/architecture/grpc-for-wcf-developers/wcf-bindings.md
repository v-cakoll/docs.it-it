---
title: Binding e trasporti WCF-gRPC per sviluppatori WCF
description: Informazioni sul confronto tra le diverse associazioni e trasporti WCF con gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: ebe324eace8f5f418b920c59f6d72eaaa686ef02
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503344"
---
# <a name="wcf-bindings-and-transports"></a>Associazioni e trasporti WCF

Windows Communication Foundation (WCF) include *Binding* incorporati che specificano protocolli di rete diversi, formati di trasmissione e altri dettagli di implementazione. gRPC ha in effetti un solo protocollo di rete e un solo formato wire. Tecnicamente è *possibile* personalizzare il formato wire, ma questo esula dall'ambito di questo libro. Probabilmente si noterà che gRPC offre la soluzione migliore nella maggior parte dei casi. 

Di seguito è riportata una breve discussione sulle associazioni WCF più rilevanti e sul modo in cui vengono confrontate con gli equivalenti in gRPC.

## <a name="nettcp"></a>NetTCP

Il binding NetTCP di WCF consente le connessioni permanenti, i messaggi di piccole dimensioni e la messaggistica bidirezionale. Ma funziona solo tra i client .NET e i server. gRPC consente la stessa funzionalità ma è supportata in più linguaggi e piattaforme di programmazione. 

gRPC dispone di molte funzionalità dell'associazione NetTCP di WCF, ma non vengono sempre implementate nello stesso modo. In WCF, ad esempio, la crittografia viene controllata tramite la configurazione e gestita nel Framework. In gRPC, la crittografia viene eseguita a livello di connessione tramite HTTP/2 su TLS.

## <a name="http"></a>HTTP

L'associazione WCF denominata BasicHttpBinding è in genere basata su testo e utilizza SOAP come formato wire. È lento rispetto all'associazione NetTCP. Viene in genere usato per garantire l'interoperabilità multipiattaforma o la connessione tramite l'infrastruttura Internet. 

L'equivalente in gRPC Usa HTTP/2 come livello di trasporto sottostante con il formato di Wire protobuf binario per i messaggi. Consente quindi di offrire prestazioni al livello di servizio NetTCP e l'interoperabilità multipiattaforma completa con tutti i moderni linguaggi di programmazione e Framework.

## <a name="named-pipes"></a>Named pipe

WCF ha fornito un'associazione *Named Pipes* per la comunicazione tra processi nello stesso computer fisico. La prima versione di ASP.NET Core gRPC non supporta le named pipe. L'aggiunta del supporto client e server per le named pipe e i socket di dominio UNIX è un obiettivo di una versione futura.

## <a name="msmq"></a>MSMQ

MSMQ è una coda di messaggi di Windows proprietaria. Il binding di WCF a MSMQ consente di attivare e dimenticare richieste da client che potrebbero essere elaborati in qualsiasi momento in futuro. gRPC non fornisce in modo nativo alcuna funzionalità della coda di messaggi. 

L'alternativa migliore consiste nell'usare direttamente un sistema di messaggistica come il bus di servizio di Azure, RabbitMQ o Kafka. È possibile implementare questa operazione con il client che inserisce i messaggi direttamente nella coda o un servizio di streaming client gRPC che accoda i messaggi.

## <a name="webhttpbinding"></a>WebHttpBinding

WebHttpBinding (noto anche come WCF REST), con gli attributi `WebGet` e `WebInvoke`, consente di sviluppare API RESTful che possono pronunciare JSON in un momento in cui questa situazione era meno comune. Se si dispone di un'API RESTful compilata con WCF REST, provare a eseguirne la migrazione a una normale applicazione API Web MVC ASP.NET Core. Questa migrazione fornirebbe la stessa funzionalità di una conversione a gRPC.

>[!div class="step-by-step"]
>[Precedente](wcf-endpoints-grpc-methods.md)
>[Successivo](rpc-types.md)
