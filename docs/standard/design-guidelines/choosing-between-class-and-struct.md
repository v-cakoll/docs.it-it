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
author: KrzysztofCwalina
ms.openlocfilehash: a47e43b2387362500d46c8e531f16d004d823c4c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778781"
---
# <a name="choosing-between-class-and-struct"></a>Scelta tra classi e struct
Una delle decisioni di progettazione di base che deve affrontare ogni finestra di progettazione di framework è se un tipo di progettazione come una classe (un tipo riferimento) o uno struct (tipo di valore). Buona conoscenza delle differenze nel comportamento dei tipi di riferimento e tipi di valore è essenziale per effettuare questa scelta.  
  
 La prima delle differenze tra i tipi di riferimento e tipi di valore verranno presi in considerazione è che i tipi di riferimento vengono allocati nell'heap e sottoposto a garbage collection, mentre i tipi di valore vengono allocati nello stack o inline nel che contiene i tipi e deallocato quando lo stack viene rimosso o quando deallocata relativo tipo contenitore. Pertanto, le allocazioni e deallocazioni di tipi di valore sono in genere più economica rispetto alle allocazioni e deallocazioni dei tipi di riferimento.  
  
 Successivamente, le matrici di riferimento sono tipi allocati out-of-line, vale a dire la matrice di elementi sono semplicemente i riferimenti alle istanze del tipo di riferimento che risiedono nell'heap. Matrici di tipi valore vengono allocate inline, vale a dire che gli elementi della matrice sono le istanze effettive del tipo di valore. Pertanto, le allocazioni e deallocazioni di matrici di tipi valore sono molto più economiche rispetto alle allocazioni e deallocazioni delle matrici di tipo riferimento. Inoltre, nella maggior parte dei casi le matrici di tipo valore presentano molto posizionamento ottimale dei riferimenti.  
  
 Differenza successiva è correlata all'utilizzo della memoria. I tipi di valore compattati quando esegue il cast a un tipo riferimento o una delle interfacce implementate. Ricevono unboxed quando esegue il cast nel tipo di valore. Poiché le finestre sono oggetti vengono allocati nell'heap e sottoposto a garbage collection, troppe operazioni conversione boxing e unboxing può avere un impatto negativo su heap, il garbage collector e infine le prestazioni dell'applicazione.  Al contrario, si verifica alcun tali boxing quando vengono eseguito il cast di tipi di riferimento. (Per altre informazioni, vedere [conversioni Boxing e Unboxing](../../csharp/programming-guide/types/boxing-and-unboxing.md)).
  
 Le assegnazioni dei tipi riferimento successivamente, copiare il riferimento, mentre le assegnazioni dei tipi valore copiare l'intero valore. Pertanto, le assegnazioni dei tipi di riferimento di grandi dimensioni sono più economiche rispetto all'assegnazione dei tipi di valori di grandi dimensioni.  
  
 Infine, i tipi di riferimento vengono passati per riferimento, mentre i tipi di valore vengono passati per valore. Le modifiche a un'istanza di un tipo riferimento influiscono su tutti i riferimenti che puntano all'istanza. Istanze del tipo di valore vengono copiate quando vengono passati per valore. Quando viene modificata un'istanza di un tipo di valore, ovviamente non influirà proprie copie. Poiché le copie non vengono create in modo esplicito dall'utente, ma vengono create in modo implicito quando gli argomenti vengono passati o i valori vengono restituiti, tipi di valore che possono essere modificati possono generare confusione a molti utenti. Pertanto, i tipi di valore devono essere non modificabili.  
  
 Come regola generale, la maggior parte dei tipi in un framework deve essere classi. Esistono tuttavia alcune situazioni in cui le caratteristiche di un tipo valore rendano più opportuno usare struct.  
  
 **✓ CONSIDER** definire una struttura invece di una classe, se le istanze del tipo sono ridotti e generalmente di breve durata o vengono comunemente incorporate in altri oggetti.  
  
 **X AVOID** che definisce uno struct, a meno che il tipo dispone di tutte le caratteristiche seguenti:  
  
- In modo logico rappresenta un singolo valore, simile ai tipi primitivi (`int`, `double`e così via.).  
  
- Ha una dimensione di istanza inferiore a 16 byte.  
  
- Non è modificabile.  
  
- Non dovrà eseguire la conversione boxing di frequente.  
  
 In tutti gli altri casi, è necessario definire i tipi come classi.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
