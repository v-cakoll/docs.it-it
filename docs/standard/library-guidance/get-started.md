---
title: Introduzione alla creazione di librerie .NET di alto livello
description: Introduzione alla compilazione di librerie .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 05466de1469fc765570b8250301e8404cd5df173
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145725"
---
# <a name="get-started"></a>Introduzione

## <a name="cross-platform-targetingcross-platform-targetingmd"></a>[Supporto multipiattaforma](./cross-platform-targeting.md)

Come usare .NET Standard e il multitargeting per creare librerie multipiattaforma. .NET viene eseguito in molte posizioni e le librerie .NET di un buon livello devono cercare di supportare il maggior numero possibile di piattaforme e sviluppatori.

## <a name="strong-namingstrong-namingmd"></a>[Denominazione sicura](./strong-naming.md)

Vengono fornite informazioni sui nomi sicuri e sui loro vantaggi e svantaggi. La scelta di un nome sicuro per una libreria .NET consente alla maggior parte degli sviluppatori di usare la libreria ed è una procedura consigliata.

## <a name="nuget-and-open-source-librariesnugetmd"></a>[Librerie open source e NuGet](./nuget.md)

Il modo migliore per creare pacchetti NuGet per le librerie .NET open source, inclusi i metadati consigliati per tutti i pacchetti pubblicati in NuGet.org.

### <a name="dependenciesdependenciesmd"></a>[Dipendenze](./dependencies.md)

NuGet semplifica l'uso di pacchetti esistenti quando si esegue la compilazione di una libreria .NET. Vengono fornite informazioni sulle cause comuni dei problemi relativi alle dipendenze NuGet e su come evitare che si verifichino.

### <a name="sourcelinksourcelinkmd"></a>[SourceLink](./sourcelink.md)

SourceLink è uno strumento straordinario che consente agli utenti della libreria .NET di esaminare il codice sorgente durante il debug. Questo articolo fornisce una panoramica di SourceLink e spiega perché è consigliabile usare questo strumento.

### <a name="publishingpublish-nuget-packagemd"></a>[Pubblicazione](./publish-nuget-package.md)

Anche se NuGet.org è il repository più noto e più usato, ci sono molte posizioni in cui pubblicare i pacchetti NuGet. Vengono fornite informazioni sui diversi repository di pacchetti NuGet disponibili e sulle procedure consigliate per la sicurezza per la pubblicazione di una libreria .NET.

## <a name="versioningversioningmd"></a>[Controllo delle versioni](./versioning.md)

Le librerie .NET di buon livello si evolvono nel tempo, con l'aggiunta di funzionalità, la correzione di bug e il miglioramento delle prestazioni nelle versioni successive. Vengono fornite informazioni sui diversi numeri di versione e su come comunicare agli sviluppatori le modifiche che causano un'interruzione.

### <a name="breaking-changesbreaking-changesmd"></a>[Modifiche che causano un'interruzione](./breaking-changes.md)

Per una libreria .NET è importante trovare un equilibrio tra la stabilità per gli utenti esistenti e l'innovazione per il futuro. Vengono fornite informazioni sui diversi tipi di modifiche che causano un'interruzione e sulle strategie per aggiungere nuove funzionalità mantenendo la compatibilità con le versioni precedenti.

>[!div class="step-by-step"]
>[Precedente](index.md)
>[Successivo](cross-platform-targeting.md)