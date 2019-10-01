---
title: Architettura di applicazioni .NET cloud native per Azure
description: Guida per la creazione di applicazioni native del cloud che sfruttano contenitori, microservizi e funzionalità senza server di Azure.
author: ardalis
ms.date: 03/07/2019
ms.openlocfilehash: 7f14a690d0153edc43f0ce7f4e91c9e9cd2c6858
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696783"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a>Architettura di applicazioni .NET cloud native per Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

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

Mac e macOS sono marchi registrati di Apple Inc.

Il logo Docker con la balena è un marchio registrato di Docker, Inc. Usato su autorizzazione.

Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.

Autori

> **Steve "ardalis" Smith** - Software Architect e Trainer - [Ardalis.com](https://ardalis.com)
>
> **Rob Vettor** -Microsoft-Principal Cloud System Architect/IP architect- [RobVettor.com](https://robvettor.com)

Partecipanti e revisori:

> **Cesar de la Torre**, responsabile del programma principale, team di .NET, Microsoft
>
> **Nish Anil**, Senior Program Manager, team di .NET, Microsoft

Editor:

> **Maira Wenzel**, Sr. Content Developer, team di .NET, Microsoft

## <a name="who-should-use-this-guide"></a>Destinatari della guida

I destinatari di questa guida sono principalmente sviluppatori, lead di sviluppo e architetti che sono interessati ad apprendere come creare applicazioni progettate per il cloud.

Un pubblico secondario è costituito da Decision Maker tecnici che pianificano di scegliere se compilare le proprie applicazioni usando un approccio nativo per il cloud.

## <a name="how-you-can-use-this-guide"></a>Come usare questa guida

Questa guida inizia definendo cloud native e introducendo un'applicazione di riferimento compilata usando principi e tecnologie native del cloud. Oltre a questi primi due capitoli, il resto del libro è suddiviso in capitoli specifici che riguardano argomenti comuni alla maggior parte delle applicazioni native del cloud. È possibile passare a uno di questi capitoli per ottenere informazioni sugli approcci nativi del cloud per:

- Accesso ai dati e ai dati
- Modelli di comunicazione
- Scalabilità e scalabilità
- Resilienza delle applicazioni
- Monitoraggio e integrità
- Identità e sicurezza
- DevOps

Questa guida è disponibile sia in formato PDF che in linea. È possibile inviare questo documento o collegamenti alla relativa versione online al team per garantire una conoscenza comune di questi argomenti. La maggior parte di questi argomenti trae vantaggio da una comprensione coerente dei principi e dei modelli sottostanti, nonché dei compromessi che interessano le decisioni correlate a questi argomenti. Il nostro obiettivo di questo documento è quello di dotare i team e i loro leader con le informazioni necessarie per prendere decisioni ben informate per l'architettura, lo sviluppo e l'hosting delle proprie applicazioni.

>[!div class="step-by-step"]
>[avanti](introduction.md)
