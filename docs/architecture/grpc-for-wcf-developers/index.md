---
title: ASP.NET Core gRPC per sviluppatori WCF-gRPC per sviluppatori WCF
description: DA SCRIVERE
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 6a5b4f6d0b47a272f7a753e22bfd61b06202944a
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919382"
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

Alcuni esempi contenuti nella presente guida vengono forniti solo a fini illustrativi e sono fittizi. Nessuna associazione o connessione reale è intenzionale o può essere presupposta.

Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo https://www.microsoft.com sono marchi delle società del gruppo Microsoft.

Il logo Docker Whale è un marchio registrato di Docker, Inc. usato dall'autorizzazione.

Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.

Autore:

> **Mark Rendle** -Chief Technical Officer- [Visual Recode](https://visualrecode.com)
>
> **Miranda Steiner** -autore tecnico

Editor:

> **Maira Wenzel** -SR Content Developer-Microsoft

## <a name="introduction"></a>Introduzione

TODO

## <a name="purpose"></a>Scopo

TODO

## <a name="who-should-use-this-guide"></a>Destinatari della guida

**Aggiorna**

I destinatari di questa guida sono gli sviluppatori, i lead di sviluppo e gli architetti WCF interessati alla migrazione di soluzioni WCF in .NET Framework 4 e versioni precedenti a ASP.NET Core 3,0 usando i servizi gRPC.

## <a name="how-you-can-use-this-guide"></a>Come usare questa guida

**Aggiorna**

Si tratta di una breve introduzione alla creazione di servizi gRPC in ASP.NET Core 3,0 con particolare riferimento a WCF come piattaforma analoga. Vengono illustrati i principi di gRPC, con la correlazione di ogni concetto alle funzionalità equivalenti di WCF e vengono fornite indicazioni per la migrazione di un'applicazione WCF esistente a gRPC. È utile anche per gli sviluppatori che hanno esperienza con WCF e vogliono apprendere gRPC per creare nuovi servizi. L'applicazione di esempio può essere usata come modello o riferimento per i propri progetti e si è liberi di copiare e riutilizzare il codice dal libro o dai relativi esempi.

È possibile inoltrare questa guida al team per aiutarlo ad acquisire una comprensione di base di queste considerazioni e opportunità. Facendo sì che tutti usino un insieme comune di termini e di principi sottostanti, si garantisce l'applicazione coerente di modelli e procedure architetturali.

## <a name="references"></a>Riferimenti

- **sito Web gRPC**  
  <https://grpc.io>
- **Scelta di .NET Core o .NET Framework per le app server**  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[avanti](introduction.md)
