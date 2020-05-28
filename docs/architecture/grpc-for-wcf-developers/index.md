---
title: ASP.NET Core gRPC per sviluppatori WCF-gRPC per sviluppatori WCF
description: Introduzione alla compilazione di servizi gRPC in ASP.NET Core 3,0 per sviluppatori WCF
ms.date: 09/02/2019
ms.openlocfilehash: 6e18ecfdb8fcbe20f71fd0a7c77076166451427a
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144357"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a>ASP.NET Core gRPC per sviluppatori WCF

![Immagine di copertina](./media/cover.png)

PUBBLICATO DA

Microsoft Developer Division, team dei prodotti .NET e Visual Studio

Una divisione di Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2019 Microsoft Corporation

Tutti i diritti sono riservati. Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.

Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore. I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.

 Alcuni esempi usati in questo documento vengono forniti a scopo puramente illustrativo e sono fittizi. Nessuna associazione reale o connessione è intenzionale o può essere desunta.

Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo <https://www.microsoft.com> sono marchi delle società del gruppo Microsoft.

Il logo Docker Whale è un marchio registrato di Docker, Inc. usato dall'autorizzazione.

Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.

Autori:

> **Mark Rendle** -Chief Technical Officer- [Visual Recode](https://visualrecode.com)
>
> **Miranda Steiner** -autore tecnico

Editor:

> **Maira Wenzel** -SR. Content Developer-Microsoft

## <a name="introduction"></a>Introduzione

gRPC è un Framework moderno per la creazione di servizi di rete e applicazioni distribuite. Immaginate le prestazioni delle associazioni Windows Communication Foundation (WCF) NetTCP, combinate con l'interoperabilità multipiattaforma di SOAP. gRPC si basa su HTTP/2 e sul protocollo di codifica dei messaggi protobuf per offrire una comunicazione a larghezza di banda ridotta e prestazioni elevate tra le applicazioni e i servizi. Supporta la generazione di codice server e client tra le piattaforme e i linguaggi di programmazione più diffusi, tra cui .NET, Java, Python, node. js, go e C++. Con il supporto di prima classe per gRPC in ASP.NET Core 3,0, insieme agli strumenti e alle librerie gRPC esistenti per .NET 4. x, è un'ottima alternativa a WCF per i team di sviluppo che vogliono adottare .NET Core nelle proprie organizzazioni.

## <a name="who-should-use-this-guide"></a>Destinatari della guida

Questa guida è stata scritta per gli sviluppatori che lavorano in .NET Framework o .NET Core che hanno usato in precedenza WCF e che stanno tentando di eseguire la migrazione delle applicazioni a un ambiente RPC moderno per .NET Core 3,0 e versioni successive. Più in generale, se si esegue l'aggiornamento o si sta valutando l'aggiornamento a .NET Core 3,0 e si vuole usare gli strumenti gRPC predefiniti, questa guida è anche utile.

## <a name="how-you-can-use-this-guide"></a>Come usare questa guida

Si tratta di una breve introduzione alla creazione di servizi gRPC in ASP.NET Core 3,0, con particolare riferimento a WCF come piattaforma analoga. Vengono illustrati i principi di gRPC, con la correlazione di ogni concetto alle funzionalità equivalenti di WCF e vengono fornite indicazioni per la migrazione di un'applicazione WCF esistente a gRPC. Questa funzionalità è utile anche per gli sviluppatori che hanno esperienza con WCF e vogliono imparare a usare gRPC per creare nuovi servizi. È possibile utilizzare le applicazioni di esempio come modello o riferimento per i propri progetti e si è liberi di copiare e riutilizzare il codice dal libro o dai relativi esempi.

È possibile inoltrare questa guida al team per aiutarlo ad acquisire una comprensione di base di queste considerazioni e opportunità. L'uso di un set comune di termini e di principi sottostanti contribuisce a garantire un'applicazione coerente di modelli e procedure di architettura.

## <a name="references"></a>Riferimenti

- **sito Web gRPC**
  <https://grpc.io>
- **Scelta tra .NET Core e .NET Framework per le app Server**
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[Avanti](introduction.md)
