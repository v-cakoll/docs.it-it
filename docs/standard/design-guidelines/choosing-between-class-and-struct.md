---
title: Scelta tra classi e struct
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df6659853e9c410ece3233cfa630c9066303a871
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="choosing-between-class-and-struct"></a>Scelta tra classi e struct
Una delle decisioni di progettazione di base che deve affrontare ogni finestra di progettazione di framework è di progettare un tipo come una classe (un tipo di riferimento) o uno struct (un tipo di valore). Buona conoscenza delle differenze nel comportamento dei tipi di riferimento e tipi di valore è essenziale per effettuare questa scelta.  
  
 Il primo differenza tra i tipi di riferimento e tipi di valore si prenderà in considerazione è che i tipi di riferimento sono allocati sull'heap e sottoposto a garbage collection, mentre i tipi di valore vengono allocati nello stack o inline in contenente i tipi e deallocato quando lo stack Rimuove o quando il tipo contenitore è Ottiene deallocata. Pertanto, le allocazioni e deallocazioni di tipi di valore sono in genere più economica rispetto alle allocazioni e deallocazioni dei tipi di riferimento.  
  
 Successivamente, le matrici di tipi di riferimento allocato out-of-line, vale a dire la matrice di elementi sono riferimenti soli alle istanze del tipo di riferimento che risiedono nell'heap. Matrici di tipi di valore vengono allocate inline, ovvero gli elementi della matrice sono le istanze effettive del tipo di valore. Pertanto, le allocazioni e deallocazioni di matrici di tipi di valore sono molto più economiche rispetto alle allocazioni e deallocazioni di matrici di tipi di riferimento. Inoltre, la maggior parte dei casi matrici di tipi valore risulta molto posizionamento ottimale dei riferimenti.  
  
 Differenza successiva è correlata all'utilizzo della memoria. Tipi di valore ottengano boxed quando esegue il cast a un tipo riferimento o una delle interfacce implementate. Ricevono unboxed quando esegue il cast al tipo di valore. Poiché le caselle sono oggetti che vengono allocati nell'heap sottoposto a garbage collection, troppo conversione boxing e unboxing può avere un impatto negativo sull'heap del garbage collector e infine le prestazioni dell'applicazione.  Al contrario, si verifica alcun tali boxing, come vengono eseguito il cast di tipi di riferimento.  
  
 Le assegnazioni di tipi di riferimento successivamente, copiare il riferimento, mentre le assegnazioni di tipi di valore copiare l'intero valore. Pertanto, le assegnazioni di tipi di riferimento di grandi dimensioni sono più economiche rispetto alla assegnazioni di tipi di valori di grandi dimensioni.  
  
 Infine, i tipi di riferimento vengono passati per riferimento, mentre i tipi di valore vengono passati per valore. Le modifiche a un'istanza di un tipo riferimento interessano tutti i riferimenti che puntano all'istanza. Istanze del tipo di valore vengono copiate quando vengono passati per valore. Quando un'istanza di un tipo di valore viene modificata, ovviamente non si applica una delle relative copie. Poiché le copie non vengono create in modo esplicito dall'utente, ma vengono create in modo implicito quando gli argomenti vengono passati o i valori vengono restituiti, è possibile che i tipi di valore che possono essere modificati possono generare confusione a molti utenti. Di conseguenza, i tipi di valore devono essere non modificabili.  
  
 Come regola generale, la maggior parte dei tipi in un framework deve essere classi. Esistono tuttavia alcune situazioni in cui le caratteristiche di un tipo valore rendano più appropriata per l'utilizzo delle strutture.  
  
 **Provare a ✓** la definizione di una struttura invece di una classe, se le istanze del tipo sono piccoli e di breve durata o vengono comunemente incorporate in altri oggetti.  
  
 **X evitare** definire una struttura, a meno che il tipo dispone di tutte le caratteristiche seguenti:  
  
-   Logicamente rappresenta un singolo valore, simile ai tipi primitivi (`int`, `double`, ecc.).  
  
-   Ha una dimensione di istanza inferiore a 16 byte.  
  
-   È non modificabile.  
  
-   Non dovrà essere boxed frequentemente.  
  
 In tutti gli altri casi, è necessario definire i tipi di classi.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida di progettazione di tipo](../../../docs/standard/design-guidelines/type.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
