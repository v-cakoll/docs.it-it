---
title: "Linguaggio di definizione dell'interfaccia: gRPC per sviluppatori WCF"
description: Introduzione all'IDL dei buffer del protocollo.
ms.date: 09/02/2019
ms.openlocfilehash: 1f304502bd0091f753a3d2f7854298f4bbf983f1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967634"
---
# <a name="interface-definition-language"></a>Linguaggio di definizione dell'interfaccia

Con WCF, i servizi possono esporre i metadati della descrizione utilizzando il linguaggio WSDL (Web Service Definition Language), generato in modo dinamico tramite reflection .NET in fase di esecuzione. Gli sviluppatori possono utilizzare questi metadati per generare client per tali servizi, potenzialmente in altre lingue se viene utilizzata un'associazione indipendente dalla piattaforma, ad esempio SOAP su HTTP.

gRPC usa il linguaggio di definizione dell'interfaccia (IDL) dai buffer del protocollo. Il buffer di protocollo IDL è un linguaggio personalizzato indipendente dalla piattaforma con una specifica aperta. Gli sviluppatori `.proto` file di codice per descrivere i servizi insieme ai relativi input e output. Questi file di `.proto` possono quindi essere usati per generare stub specifici della lingua o della piattaforma per client e server, consentendo la comunicazione di più piattaforme diverse. Condividendo `.proto` file, i team possono generare codice per usare i servizi di altri utenti senza dover prendere una dipendenza dal codice.

Uno dei vantaggi di protobuf IDL è che, come linguaggio personalizzato, consente a gRPC di essere completamente indipendente dal linguaggio e dalla piattaforma, non privilegiando alcuna tecnologia rispetto a un altro.

Protobuf IDL è anche progettato per gli utenti sia in lettura che in scrittura, mentre WSDL è concepito come formato leggibile dal computer/scrivibile. Per modificare il WSDL di un servizio WCF è in genere necessario apportare le modifiche al codice del servizio stesso, eseguendo il servizio e rigenerando il file WSDL dal server. Al contrario, con un file di `.proto`, le modifiche sono semplici da applicare con un editor di testo e passano automaticamente attraverso il codice generato. Visual Studio 2019 compila i file `.proto` in background quando vengono salvati; Quando si usano altri editor, ad esempio VS Code le modifiche verranno applicate al momento della compilazione del progetto.

Se confrontato con XML e in particolare SOAP, i messaggi codificati con protobuf presentano molti vantaggi. I messaggi protobuf tendono a essere più piccoli rispetto agli stessi dati serializzati come XML SOAP e la codifica, la decodifica e la trasmissione in rete possono essere più veloci.

Il potenziale svantaggio di protobuf rispetto a SOAP è che, poiché i messaggi non sono leggibili, è necessario disporre di strumenti aggiuntivi per eseguire il debug del contenuto del messaggio.

> [!TIP]
> gRPC *supporta la reflection* del server per l'accesso dinamico ai servizi senza stub precompilati, sebbene sia più adatto per strumenti di uso generico rispetto ai client specifici dell'applicazione. Per ulteriori informazioni sulla reflection del server gRPC, vedere il repository [gRPC/gRPC](https://github.com/grpc/grpc/blob/master/doc/server-reflection.md) su GitHub.

> [!NOTE]
> Il formato binario di WCF, utilizzato con l'associazione NetTCP, è molto più vicino a protobuf in termini di compattezza e prestazioni, ma NetTCP è utilizzabile solo tra client e server .NET, mentre protobuf è una soluzione multipiattaforma.

>[!div class="step-by-step"]
>[Precedente](approach.md)
>[Successivo](network-protocols.md)
