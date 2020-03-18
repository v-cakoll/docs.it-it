---
title: Architettura delle applicazioni .NET native cloud per AzureArchitecting Cloud Native .NET Applications for Azure
description: Guida per la creazione di applicazioni native nel cloud sfruttando contenitori, microservizi e funzionalità senza server di Azure.A guide for building cloud-native applications leveraging containers, microservices, and serverless features of Azure.
author: ardalis
ms.date: 03/07/2019
ms.openlocfilehash: 7f14a690d0153edc43f0ce7f4e91c9e9cd2c6858
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71696783"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a>Architettura delle applicazioni .NET native cloud per AzureArchitecting Cloud Native .NET Applications for Azure

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

 Alcuni esempi usati in questo documento vengono forniti a scopo puramente illustrativo e sono fittizi. Nessuna associazione reale o connessione è intenzionale o può essere desunta.

Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo https://www.microsoft.com sono marchi delle società del gruppo Microsoft.

Mac e macOS sono marchi registrati di Apple Inc.

Il logo Docker whale è un marchio registrato di Docker, Inc.

Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.

Autori:

> **Steve "ardalis" Smith** - Software Architect e Trainer - [Ardalis.com](https://ardalis.com)
>
> **Rob Vettor** - Microsoft - Principal Cloud System Architect/IP Architect - [RobVettor.com](https://robvettor.com)

Partecipanti e revisori:

> **Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft
>
> **Nish Anil**, Senior Program Manager, team di .NET, Microsoft

Editor:

> **Maira Wenzel**, Sr. Content Developer, Team .NET, Microsoft

## <a name="who-should-use-this-guide"></a>Destinatari della guida

Il pubblico di questa guida è composto principalmente da sviluppatori, responsabili dello sviluppo e architetti interessati a imparare a creare applicazioni progettate per il cloud.

Un pubblico secondario è un pubblico tecnico che prevede di scegliere se creare le proprie applicazioni utilizzando un approccio cloud-native.

## <a name="how-you-can-use-this-guide"></a>Come usare questa guida

Questa guida inizia definendo cloud nativo e introducendo un'applicazione di riferimento creata utilizzando principi e tecnologie native cloud. Al di là di questi primi due capitoli, il resto del libro è suddiviso in capitoli specifici incentrati su argomenti comuni alla maggior parte delle applicazioni native nel cloud. È possibile passare a uno qualsiasi di questi capitoli per informazioni sugli approcci nativi al cloud:

- Accesso ai dati e ai dati
- Modelli di comunicazione
- Scalabilità e scalabilità
- Resilienza delle applicazioni
- Monitoraggio e integrità
- Identità e sicurezza
- DevOps

Questa guida è disponibile sia in formato PDF che online. Sentitevi liberi di inoltrare questo documento o collegamenti alla sua versione online al vostro team per contribuire a garantire una comprensione comune di questi argomenti. La maggior parte di questi argomenti beneficiano di una comprensione coerente dei principi e dei modelli sottostanti, nonché dei compromessi coinvolti nelle decisioni relative a questi argomenti. Il nostro obiettivo con questo documento è quello di dotare i team e i loro leader delle informazioni di cui hanno bisogno per prendere decisioni ben informate per l'architettura, lo sviluppo e l'hosting delle loro applicazioni.

>[!div class="step-by-step"]
>[Avanti](introduction.md)
