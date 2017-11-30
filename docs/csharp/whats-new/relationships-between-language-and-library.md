---
title: "La relazione tra le funzionalità del linguaggio e i tipi della libreria | Documenti Microsoft"
description: "Funzionalità del linguaggio spesso si basano sui tipi di raccolta per l'implementazione. Comprendere la relazione."
keywords: Progettazione del linguaggio c#, libreria standard
author: billwagner
ms.author: wiwagn
ms.date: 07/20/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 93fd26a72743fcf45df3904cb8d0c787d8a228a8
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2017
---
# <a name="relationships-between-language-features-and-library-types"></a>Relazioni tra le funzionalità del linguaggio e i tipi di librerie

La definizione del linguaggio c# richiede una libreria standard di determinati tipi e membri accessibili di tali tipi. Il compilatore genera codice che usa questi tipi richiesti e i membri per numerose funzionalità diverse. Quando necessario, sono disponibili i pacchetti NuGet che contengono i tipi necessari per le versioni più recenti del linguaggio durante la scrittura di codice per gli ambienti in cui tali tipi o membri non sono stati distribuiti ancora.

Questa dipendenza dalla funzionalità della libreria standard è stato incluso nel linguaggio c# fin dalla prima versione. In questa versione, inclusi esempi:

* <xref:System.Exception>-utilizzato per tutte le eccezioni generate dal compilatore.
* <xref:System.String>-C# `string` tipo è un sinonimo per <xref:System.String>.
* <xref:System.Int32>-sinonimo di `int`.

La prima versione è semplice: il compilatore e la libreria standard fornita insieme e non c'è solo una versione di ogni.

Le versioni successive del linguaggio c# occasionalmente aggiunti nuovi tipi o membri per le dipendenze. Gli esempi includono: <xref:System.Runtime.CompilerServices.INotifyCompletion>, <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> e <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>. C# 7.0 questo continua mediante l'aggiunta di una dipendenza su <xref:System.ValueTuple> per implementare il [Tuple](../tuples.md) funzionalità del linguaggio.

Il team di progettazione del linguaggio funziona per ridurre al minimo la superficie dei tipi e membri necessari in una libreria standard di conformità. Tale obiettivo è bilanciato tra una progettazione in cui nuove funzionalità della libreria sono state incorporate senza problemi nel linguaggio. Esistere nuove funzionalità nelle versioni future di c# che richiedono nuovi tipi e membri in una libreria standard. È importante comprendere come gestire tali dipendenze il lavoro.

## <a name="managing-your-dependencies"></a>La gestione delle dipendenze

Strumenti del compilatore c# sono ora disaccoppiati dal ciclo di rilascio delle librerie .NET sulle piattaforme supportate. In effetti, diverse librerie .NET sono cicli di rilascio diversi: .NET Framework in Windows è relesed come un aggiornamento di Windows, .NET Core è disponibile su una pianificazione separata e le versioni di Xamarin di spedizione gli aggiornamenti di libreria con gli strumenti di Xamarin per ciascuna piattaforma di destinazione.

La maggior parte del tempo, non noterai queste modifiche. Quando si lavora con una versione più recente del linguaggio che richiede alcune funzionalità non ancora presenti le librerie .NET su questa piattaforma, tuttavia, sarà fanno riferimento i pacchetti NuGet per fornire i nuovi tipi.
Come le piattaforme supporta le app viene aggiornato con le nuove installazioni di framework, è possibile rimuovere il riferimento aggiuntivo.

Questa separazione, significa che è possibile usare nuove funzionalità del linguaggio, anche quando si dispone di macchine che potrebbero non avere framework corrispondente.
