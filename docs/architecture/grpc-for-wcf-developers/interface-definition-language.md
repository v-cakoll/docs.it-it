---
title: "Linguaggio di definizione dell'interfaccia: gRPC per sviluppatori WCF"
description: Introduzione all'IDL dei buffer del protocollo.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 71bdf8bf488e0a5bed177817343051bcd7847d25
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184428"
---
# <a name="interface-definition-language"></a>Linguaggio di definizione dell'interfaccia

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Con WCF, i servizi possono esporre i metadati della descrizione utilizzando il linguaggio WSDL (Web Service Definition Language), generato in modo dinamico tramite reflection .NET in fase di esecuzione. Gli sviluppatori possono utilizzare questi metadati per generare client per tali servizi, potenzialmente in altre lingue se viene utilizzata un'associazione indipendente dalla piattaforma, ad esempio SOAP su HTTP.

gRPC usa il linguaggio di definizione dell'interfaccia (IDL) dai buffer del protocollo. Il buffer di protocollo IDL è un linguaggio personalizzato indipendente dalla piattaforma con una specifica aperta. Consente agli sviluppatori di `.proto` usare file di codice per descrivere i servizi insieme ai relativi input e output. Questi `.proto` file possono quindi essere usati per generare stub specifici della lingua o della piattaforma per client e server, consentendo la comunicazione di più piattaforme diverse. Grazie alla `.proto` condivisione di file, i team possono generare codice per usare i servizi di altri utenti senza dover prendere una dipendenza dal codice.

Uno dei vantaggi di protobuf IDL è che, come linguaggio personalizzato, consente a gRPC di essere completamente indipendente dal linguaggio e dalla piattaforma, non privilegiando alcuna tecnologia rispetto a un altro.

Protobuf IDL è anche progettato per gli utenti sia in lettura che in scrittura, mentre WSDL è concepito come formato leggibile dal computer/scrivibile. Per modificare il WSDL di un servizio WCF è in genere necessario apportare le modifiche al codice del servizio stesso, eseguendo il servizio e rigenerando il file WSDL dal server. Al contrario, con un `.proto` file, le modifiche sono semplici da applicare con un editor di testo e passano automaticamente attraverso il codice generato. Visual Studio 2019 Compila `.proto` i file in background quando vengono salvati. quando si usano altri editor, ad esempio vs code le modifiche verranno applicate al momento della compilazione del progetto.

Se confrontato con XML e in particolare SOAP, i messaggi codificati con protobuf presentano molti vantaggi. I messaggi protobuf tendono a essere più piccoli rispetto agli stessi dati serializzati come XML SOAP e la codifica, la decodifica e la trasmissione in rete possono essere più veloci.

Il potenziale svantaggio di protobuf rispetto a SOAP è che, poiché i messaggi non sono leggibili, è necessario disporre di strumenti aggiuntivi per eseguire il debug del contenuto del messaggio.

> [!TIP]
> gRPC *supporta la reflection* del server per l'accesso dinamico ai servizi senza stub precompilati, sebbene sia più adatto per strumenti di uso generico rispetto ai client specifici dell'applicazione. Per ulteriori informazioni sulla reflection del server gRPC, vedere il repository [gRPC/gRPC](https://github.com/grpc/grpc/blob/master/doc/server-reflection.md) su GitHub.

> [!NOTE]
> Il formato binario di WCF, utilizzato con l'associazione NetTCP, è molto più vicino a protobuf in termini di compattezza e prestazioni, ma NetTCP è utilizzabile solo tra client e server .NET, mentre protobuf è una soluzione multipiattaforma.

>[!div class="step-by-step"]
>[Precedente](approach.md)
>[Successivo](network-protocols.md)
