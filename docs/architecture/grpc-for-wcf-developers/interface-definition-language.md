---
title: "Linguaggio di definizione dell'interfaccia: gRPC per sviluppatori WCF"
description: Introduzione all'IDL dei buffer del protocollo.
ms.date: 09/02/2019
ms.openlocfilehash: 841f041ae350e76e648c71f9d6d113b9d39e0d3b
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543209"
---
# <a name="interface-definition-language"></a>Linguaggio di definizione dell'interfaccia

Con Windows Communication Foundation (WCF), i servizi possono esporre i metadati della descrizione utilizzando il linguaggio WSDL (Web Service Definition Language). WSDL viene generato dinamicamente usando la reflection .NET in fase di esecuzione. Gli sviluppatori possono utilizzare questi metadati per generare client per tali servizi, potenzialmente in altre lingue se utilizzano un'associazione indipendente dalla piattaforma, ad esempio SOAP su HTTP.

gRPC usa il linguaggio di definizione dell'interfaccia (IDL) dai buffer del protocollo. Il buffer di protocollo IDL è un linguaggio personalizzato indipendente dalla piattaforma con una specifica aperta. Gli sviluppatori creano `.proto` file per descrivere i servizi, insieme ai rispettivi input e output. Questi file di `.proto` possono quindi essere usati per generare stub specifici della lingua o della piattaforma per client e server, consentendo la comunicazione di più piattaforme diverse. Grazie alla condivisione di file di `.proto`, i team possono generare codice per usare i servizi di altri, senza dover prendere una dipendenza dal codice.

Uno dei vantaggi di protobuf IDL è che, come linguaggio personalizzato, consente a gRPC di essere completamente indipendente dal linguaggio e dalla piattaforma, non privilegiando alcuna tecnologia rispetto a un altro.

Protobuf IDL è anche progettato per gli utenti sia in lettura che in scrittura, mentre WSDL è concepito come formato leggibile dal computer/scrivibile. Per modificare il WSDL di un servizio WCF è in genere necessario modificare il servizio, eseguendo il servizio e rigenerando il file WSDL dal server. Al contrario, con un file di `.proto`, le modifiche sono semplici da applicare con un editor di testo e passano automaticamente attraverso il codice generato. Visual Studio 2019 compila i file `.proto` in background quando vengono salvati. Con altri editor, ad esempio VS Code, le modifiche vengono applicate al momento della compilazione del progetto.

Se confrontato con XML e in particolare SOAP, i messaggi codificati con protobuf presentano molti vantaggi. I messaggi protobuf tendono a essere più piccoli rispetto agli stessi dati serializzati come XML SOAP e la codifica, la decodifica e la trasmissione su una rete possono essere più veloci.

Il potenziale svantaggio di protobuf rispetto a SOAP è che, poiché i messaggi non sono leggibili dagli utenti, è necessario disporre di strumenti aggiuntivi per eseguire il debug del contenuto del messaggio.

> [!TIP]
> gRPC *supporta la reflection* server per l'accesso dinamico ai servizi senza stub pre-compilati, sebbene sia più adatto per strumenti generici rispetto ai client specifici dell'applicazione. Per altre informazioni, vedere [GRPC server Reflection Protocol](https://github.com/grpc/grpc/blob/master/doc/server-reflection.md) su GitHub.

> [!NOTE]
> Il formato binario di WCF, utilizzato con l'associazione NetTCP, è molto più vicino a protobuf in termini di compattezza e prestazioni. Tuttavia, NetTCP è utilizzabile solo tra client e server .NET, mentre protobuf è una soluzione multipiattaforma.

>[!div class="step-by-step"]
>[Precedente](approach.md)
>[Successivo](network-protocols.md)
