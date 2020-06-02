---
title: Scelta tra classi e struct
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- class library design guidelines [.NET Framework], classes
- structures [.NET Framework], vs. classes
- classes [.NET Framework], design guidelines
- type design guidelines, structures
- structures [.NET Framework], design guidelines
- classes [.NET Framework], vs. structures
- type design guidelines, classes
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
ms.openlocfilehash: 4b4a619214fe6ba49f21a88cd132dcb3f2704608
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280361"
---
# <a name="choosing-between-class-and-struct"></a>Scelta tra classi e struct
Una delle decisioni di progettazione di base ogni volto di progettazione Framework è se progettare un tipo come classe (un tipo di riferimento) o come struct (tipo valore). Una migliore comprensione delle differenze nel comportamento dei tipi di riferimento e dei tipi di valore è essenziale per la scelta.

 La prima differenza tra i tipi di riferimento e i tipi di valore che consideriamo è che i tipi di riferimento vengono allocati nell'heap e sottoposti a Garbage Collection, mentre i tipi di valore vengono allocati nello stack o inline in che contengono tipi e deallocati quando lo stack viene rimosso o quando il tipo contenitore viene deallocato. Pertanto, le allocazioni e le deallocazioni di tipi di valore sono in genere più convenienti rispetto alle allocazioni e alle deallocazioni dei tipi di riferimento.

 Successivamente, le matrici di tipi di riferimento vengono allocate fuori riga, ovvero gli elementi della matrice sono solo riferimenti a istanze del tipo di riferimento che risiedono nell'heap. Le matrici di tipi di valore vengono allocate inline, vale a dire che gli elementi della matrice sono le istanze effettive del tipo di valore. Pertanto, le allocazioni e le deallocazioni di matrici di tipi di valore sono molto più convenienti delle allocazioni e delle deallocazioni di matrici di tipi di riferimento. Inoltre, nella maggior parte dei casi, le matrici di tipi di valore presentano una maggiore località di riferimento.

 La differenza successiva riguarda l'utilizzo della memoria. Quando si esegue il cast a un tipo di riferimento o a una delle interfacce implementate, i tipi di valore ottengono il Boxing. Ottengono unboxed quando viene eseguito il cast al tipo di valore. Poiché le caselle sono oggetti allocati nell'heap e vengono sottoposti a Garbage Collection, un numero eccessivo di operazioni di Boxing e unboxing può avere un impatto negativo sull'heap, il Garbage Collector e infine le prestazioni dell'applicazione.  Al contrario, non viene eseguita la conversione boxing in quanto viene eseguito il cast di tipi di riferimento. Per ulteriori informazioni, vedere [Boxing e unboxing](../../csharp/programming-guide/types/boxing-and-unboxing.md).

 Le assegnazioni dei tipi di riferimento, quindi, copiano il riferimento, mentre le assegnazioni dei tipi di valore copiano l'intero valore. Pertanto, le assegnazioni di tipi di riferimento di grandi dimensioni sono più convenienti rispetto alle assegnazioni di tipi di valore di grandi dimensioni.

 Infine, i tipi di riferimento vengono passati per riferimento, mentre i tipi di valore vengono passati per valore. Le modifiche apportate a un'istanza di un tipo riferimento influiscono su tutti i riferimenti che puntano all'istanza. Le istanze del tipo di valore vengono copiate quando vengono passate per valore. Quando viene modificata un'istanza di un tipo di valore, ovviamente non influisce sulle copie. Poiché le copie non vengono create in modo esplicito dall'utente, ma vengono create in modo implicito quando gli argomenti vengono passati o vengono restituiti valori restituiti, i tipi di valore che possono essere modificati possono generare confusione per molti utenti. Pertanto, i tipi di valore non devono essere modificabili.

 Come regola generale, la maggior parte dei tipi in un Framework deve essere una classe. In alcune situazioni, tuttavia, le caratteristiche di un tipo di valore rendono più appropriato utilizzare gli struct.

 ✔️ CONSIGLIABILE definire uno struct anziché una classe se le istanze del tipo sono di dimensioni ridotte e di breve durata o sono comunemente incorporate in altri oggetti.

 ❌EVITARE di definire uno struct, a meno che il tipo non abbia tutte le caratteristiche seguenti:

- Rappresenta logicamente un singolo valore, simile ai tipi primitivi ( `int` , `double` e così via).

- Ha una dimensione di istanza inferiore a 16 byte.

- Non è modificabile.

- Non sarà necessario eseguire la conversione boxing di frequente.

 In tutti gli altri casi, è necessario definire i tipi come classi.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di tipi](type.md)
- [Linee guida per la progettazione di Framework](index.md)
