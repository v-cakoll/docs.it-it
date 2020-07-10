---
title: Relazione tra funzionalità del linguaggio e tipi di libreria | Microsoft Docs
description: Le funzionalità del linguaggio spesso si basano sui tipi di libreria per l'implementazione. Comprendere la relazione.
ms.date: 07/20/2017
ms.openlocfilehash: abf15385da3756c35db2df822cc2e11e9edf5758
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174101"
---
# <a name="relationships-between-language-features-and-library-types"></a>Relazioni tra funzionalità del linguaggio e tipi di libreria

La definizione del linguaggio C# richiede che una libreria standard includa determinati tipi e specifici membri accessibili per tali tipi. Il compilatore genera codice che usa questi tipi e membri richiesti per numerose funzionalità del linguaggio diverse. Quando necessario, sono disponibili pacchetti NuGet che contengono i tipi necessari per le versioni più recenti del linguaggio durante la scrittura di codice per gli ambienti in cui tali tipi o membri non sono ancora stati distribuiti.

Questa dipendenza dalla funzionalità della libreria standard fa parte del linguaggio C# fin dalla prima versione. Alcuni esempi in quella versione sono i seguenti:

* <xref:System.Exception> - usato per tutte le eccezioni generate dal compilatore.
* <xref:System.String> - il tipo C# `string` è sinonimo di <xref:System.String>.
* <xref:System.Int32> - sinonimo di `int`.

La prima versione era semplice: il compilatore e la libreria standard erano forniti assieme ed esisteva una sola versione di ognuno.

Nelle versioni successive del linguaggio C# sono stati aggiunti occasionalmente nuovi tipi o membri alle dipendenze. Alcuni esempi sono <xref:System.Runtime.CompilerServices.INotifyCompletion>, <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> o <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>. C# 7.0 continua in questa direzione aggiungendo una dipendenza per <xref:System.ValueTuple> per implementare la funzionalità del linguaggio [tuple](../language-reference/builtin-types/value-tuples.md).

Il team di progettazione del linguaggio si impegna per ridurre al minimo la superficie di tipi e membri richiesti in una libreria standard conforme. Tale obiettivo deve convivere con l'esigenza di realizzare una progettazione lineare che consenta il facile incorporamento delle nuove funzionalità della libreria nel linguaggio. Le versioni future di C# includeranno nuove funzionalità che richiedono nuovi tipi e membri in una libreria standard. È importante comprendere come gestire tali dipendenze nel lavoro di sviluppo.

## <a name="managing-your-dependencies"></a>Gestione delle dipendenze

Gli strumenti del compilatore C# sono ora separati dal ciclo di rilascio delle librerie .NET nelle piattaforme supportate. In effetti, le diverse librerie .NET hanno cicli di rilascio diversi: .NET Framework in Windows viene rilasciato come aggiornamento di Windows, .NET Core viene distribuito con una pianificazione separata e le versioni di Xamarin degli aggiornamenti delle librerie vengono forniti con gli strumenti di Xamarin per ogni piattaforma di destinazione.

Nella maggior parte dei casi, non si noteranno queste differenze. Quando si lavora con una versione più recente del linguaggio che richiede funzionalità non ancora presenti nelle librerie .NET nella piattaforma, tuttavia, sarà necessario fare riferimento ai pacchetti NuGet per fornire i nuovi tipi.
Dato che le piattaforme supportate dall'app vengono aggiornate con le nuove installazioni dei framework, è possibile rimuovere il riferimento aggiuntivo.

Questa separazione significa che è possibile usare le nuove funzionalità del linguaggio, anche quando i computer di destinazione potrebbero non disporre del framework corrispondente.
