---
title: Panoramica della programmazione asincrona
description: Informazioni che illustrano che la programmazione asincrona è una tecnica fondamentale che semplifica la gestione di pesanti operazioni I/O simultanee su diversi core.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 1e38e9d9-8284-46ee-a15f-199adc4f26f4
ms.openlocfilehash: d649bc3a92d3bb834b3bc4f7d3c1bcb0f9417375
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159728"
---
# <a name="async-overview"></a>Panoramica della programmazione asincrona

Fino a non molto tempo fa, per avere app più veloci bastava acquistare un nuovo PC o server. Ad un certo punto, però, questa tendenza si è fermata. Anzi, si è invertita. Sono comparsi telefoni cellulari con chip ARM a core singolo da 1ghz e i carichi di lavoro dei server si sono spostati sulle macchine virtuali. Gli utenti vogliono interfacce a velocità di risposta elevata e i titolari di business vogliono server scalabili in base alle loro attività aziendali. Il passaggio ai dispositivi mobili e cloud e una popolazione connessa a Internet che ormai supera i 3 miliardi di utenti, hanno avuto come risultato lo sviluppo di nuovi modelli di software.

- Ci si aspetta che le applicazioni client siano sempre attive, sempre connesse e costantemente reattive all'interazione dell'utente, ad esempio al tocco, con valutazioni dell'archivio applicazioni sempre ottime.
- Ci si attende dai servizi che sappiano gestire i picchi di traffico scalando verticalmente e orizzontalmente senza intoppi.

La programmazione asincrona è una tecnica fondamentale che semplifica la gestione di pesanti operazioni I/O simultanee su diversi core. .NET offre funzionalità per le app e i servizi che possono essere reattive ed elastiche con modelli di programmazione asincrona a livello di linguaggio facili C#da usare in, F#Visual Basic e.

## <a name="why-write-async-code"></a>Perché scrivere codice asincrono?

Le app moderne fanno un uso intensivo di I/O file e rete. Le API I/O solitamente si bloccano per impostazione predefinita, con conseguenti esperienze utente e uso dell'hardware poco soddisfacenti, a meno che non si voglia imparare a usare modelli complessi. Le API asincrone basate su attività e il modello di programmazione asincrona a livello di linguaggio invertono questa tendenza, rendendo l'esecuzione asincrona predefinita, con pochi concetti nuovi da apprendere.

Il codice asincrono ha le caratteristiche seguenti:

- Gestisce più richieste server cedendo i thread per gestire più richieste durante l'attesa del ritorno delle richieste I/O.
- Consente alle interfacce utente di essere più reattive, cedendo thread all'interazione dell'interfaccia utente durante l'attesa delle richieste I/O e spostando le attività con esecuzione prolungata ad altri core della CPU.
- Molte delle API di .NET più recenti sono asincrone.
- Scrivere codice asincrono in .NET è facile.

## <a name="whats-next"></a>Quali sono le operazioni successive?

Per altre informazioni, vedere l'argomento [La programmazione asincrona in dettaglio](async-in-depth.md).

L'argomento [Modelli di programmazione asincrona](asynchronous-programming-patterns/index.md) offre una panoramica dei tre modelli di programmazione asincroni supportati in .NET:  
  
- [Asynchronous Programming Model (APM)](asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (Modello di programmazione asincrona, APM - legacy)  
  
- [Event-based Asynchronous Pattern (EAP)](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi - legacy)  
  
- [Task-based Asynchronous Pattern (TAP)](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Modello asincrono basato su attività - Consigliato per nuove attività di sviluppo)  

Per altre informazioni sul modello di programmazione basato su attività consigliato, vedere l'argomento [Programmazione asincrona basata su attività](parallel-programming/task-based-asynchronous-programming.md).
