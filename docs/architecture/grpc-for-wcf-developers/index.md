---
title: ASP.NET Core gRPC per gli sviluppatori WCF - gRPC per gli sviluppatori WCF
description: Introduzione alla creazione di servizi gRPC in ASP.NET Core 3.0 per gli sviluppatori WCFIntroduction to building gRPC services in ASP.NET Core 3.0 for WCF developers
ms.date: 09/02/2019
ms.openlocfilehash: 175dfbf1880a0937615543c248fba3bed0e25c23
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988960"
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

Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo https://www.microsoft.com sono marchi delle società del gruppo Microsoft.

Il logo Docker whale è un marchio registrato di Docker, Inc.

Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.

Autori:

> **Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)
>
> **Miranda Steiner** - Autore Tecnico

Editor:

> **Maira Wenzel** - Sr. Content Developer - Microsoft

## <a name="introduction"></a>Introduzione

gRPC è un framework moderno per la creazione di servizi in rete e applicazioni distribuite. Si immaginino le prestazioni delle associazioni NetTCP di Windows Communication Foundation (WCF), combinate con l'interoperabilità multipiattaforma di SOAP. gRPC si basa su HTTP/2 e sul protocollo di codifica dei messaggi Protobuf per fornire comunicazioni ad alte prestazioni e a larghezza di banda ridotta tra applicazioni e servizi. Supporta la generazione di codice server e client tra i linguaggi di programmazione più diffusi e le piattaforme, tra cui .NET, Java, Python, Node.js, Go e C . Con il supporto di prima classe per gRPC in ASP.NET Core 3.0, insieme agli strumenti e alle librerie gRPC esistenti per .NET 4.x, è un'ottima alternativa a WCF per i team di sviluppo che desiderano adottare .NET Core nelle proprie organizzazioni.

## <a name="who-should-use-this-guide"></a>Destinatari della guida

Questa guida è stata scritta per gli sviluppatori che lavorano in .NET Framework o .NET Core che hanno utilizzato in precedenza WCF e che stanno cercando di eseguire la migrazione delle applicazioni in un ambiente RPC moderno per .NET Core 3.0 e versioni successive. Più in generale, se si esegue l'aggiornamento o si sta valutando l'aggiornamento a .NET Core 3.0 e si desidera utilizzare gli strumenti gRPC incorporati, questa guida è utile.

## <a name="how-you-can-use-this-guide"></a>Come usare questa guida

Si tratta di una breve introduzione alla creazione di servizi gRPC in ASP.NET Core 3.0, con particolare riferimento a WCF come piattaforma analoga. Vengono illustrati i principi di gRPC, si correlano ogni concetto alle funzionalità equivalenti di WCF e vengono fornite indicazioni per la migrazione di un'applicazione WCF esistente a gRPC. È utile anche per gli sviluppatori che hanno esperienza con WCF e stanno cercando di imparare gRPC per creare nuovi servizi. È possibile utilizzare le applicazioni di esempio come modello o riferimento per i propri progetti e si è liberi di copiare e riutilizzare il codice dal libro o dai relativi esempi.

È possibile inoltrare questa guida al team per aiutarlo ad acquisire una comprensione di base di queste considerazioni e opportunità. Avere tutti coloro che lavorano da un insieme comune di termini e principi sottostanti aiuta a garantire un'applicazione coerente dei modelli e delle pratiche architettoniche.

## <a name="references"></a>Riferimenti

- **Sito Web gRPC**
  <https://grpc.io>
- **Scelta tra .NET Core e .NET Framework per le app server**
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[Avanti](introduction.md)
