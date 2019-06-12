---
title: Riferimenti per C#
ms.date: 02/14/2017
helpviewer_keywords:
- Visual C#, language reference
- language reference [C#]
- Programmer's Reference for C#
- C# language, reference
- reference, C# language
ms.assetid: 06de3167-c16c-4e1a-b3c5-c27841d4569a
ms.openlocfilehash: 45352d97372e556627ead75d969f088de9c85bd0
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833242"
---
# <a name="c-reference"></a>Riferimenti per C#
Questa sezione offre informazioni di riferimento su parole chiave, operatori, caratteri speciali, direttive del preprocessore, opzioni del compilatore ed errori e avvisi del compilatore in C#.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Parole chiave di C#](../../csharp/language-reference/keywords/index.md)  
 Fornisce collegamenti a informazioni su sintassi e parole chiave di C#.  
  
 [Operatori C#](../../csharp/language-reference/operators/index.md)  
 Fornisce collegamenti a informazioni su sintassi e operatori di C#.  

 [Caratteri speciali di C#](../../csharp/language-reference/tokens/index.md)  
 Fornisce collegamenti a informazioni sui caratteri speciali contestuali di C# e sul relativo utilizzo.  

 [Direttive per il preprocessore C#](../../csharp/language-reference/preprocessor-directives/index.md)  
 Fornisce collegamenti a informazioni sui comandi del compilatore per l'incorporamento nel codice sorgente C#.  
  
 [Opzioni del compilatore C#](../../csharp/language-reference/compiler-options/index.md)  
 Include informazioni sulle opzioni del compilatore e su come usarle.  
  
 [Errori del compilatore C#](../../csharp/language-reference/compiler-messages/index.md)  
 Include frammenti di codice che illustrano la causa e la correzione per gli errori del compilatore e gli avvisi di C#.  
  
 [Specifiche del linguaggio C#](../../../_csharplang/spec/introduction.md)  
 Specifica del linguaggio C# 6.0. Si tratta di una proposta bozza per il linguaggio C# 6.0. La versione 5.0 è stata rilasciata a dicembre 2017 come documento [Standard ECMA-334 5th Edition](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf).

Le funzionalità che sono state implementate nelle versioni di C# successive alla 6.0 sono rappresentate in proposte di specifica del linguaggio. Questi documenti descrivono i progetti per la specifica del linguaggio per l'aggiunta di queste nuove funzionalità.

 [Proposte per il linguaggio C# 7.0](../../../_csharplang/proposals/csharp-7.0/pattern-matching.md)  
 Esistono varie nuove funzionalità implementate in C# 7.0, tra le quali criteri di ricerca, funzioni locali, dichiarazioni di variabili out, espressioni throw, valori letterali binari e separatori di cifre. Questa cartella contiene le specifiche per ognuna di tali funzionalità.
  
 [Proposte per il linguaggio C# 7.1](../../../_csharplang/proposals/csharp-7.1/async-main.md)  
 In C# 7.1 sono state aggiunte nuove funzionalità. Prima di tutto, è possibile scrivere un metodo `Main` che restituisce `Task` o `Task<int>`. In questo modo è possibile aggiungere il modificatore `async` a `Main`. L'espressione `default` può essere usata senza un tipo nelle posizioni in cui il tipo può essere dedotto. Possono essere dedotti anche i nomi dei membri delle tuple. Infine, è possibile usare criteri di ricerca con generics.

 [Proposte per il linguaggio C# 7.2](../../../_csharplang/proposals/csharp-7.2/readonly-ref.md)  
 In C# 7.2 sono state aggiunte varie piccole funzionalità. È possibile passare argomenti per riferimento di sola lettura tramite la parola chiave `in`. Sono state introdotte numerose modifiche di basso livello per supportare la sicurezza in fase di compilazione per `Span` e i tipi correlati. È possibile usare argomenti denominati in cui gli argomenti successivi sono posizionali, in alcune situazioni. Il modificatore di accesso `private protected` consente di specificare che i chiamanti sono limitati ai tipi derivati implementati nello stesso assembly. L' operatore `?:` può essere risolto come riferimento a una variabile. È anche possibile formattare i numeri esadecimali e binari usando un separatore di cifra iniziale.

 [Proposte per il linguaggio C# 7.3](../../../_csharplang/proposals/csharp-7.3/blittable.md)  
 C# 7.3 è un'altra versione secondaria che include numerosi piccoli aggiornamenti. È possibile usare nuovi vincoli per i parametri di tipo generico. Altre modifiche rendono più facile lavorare con i campi `fixed`, incluso l'uso delle allocazioni [`stackalloc`](./operators/stackalloc.md). Le variabili locali dichiarate con la parola chiave `ref` potrebbero essere riassegnate per fare riferimento alla nuova risorsa di archiviazione. È possibile posizionare attributi in proprietà implementate automaticamente destinate al campo di supporto generato dal compilatore. È possibile usare variabili di espressione negli inizializzatori. Le tuple possono essere confrontate per verificarne l'uguaglianza (o la disuguaglianza). Sono stati introdotti anche alcuni miglioramenti per la risoluzione dell'overload.
  
 [Proposte per il linguaggio C# 8.0](../../../_csharplang/proposals/csharp-8.0/nullable-reference-types.md) C# 8.0 è disponibile in anteprima. Le proposte seguenti corrispondono alle versioni correnti delle specifiche per tali funzionalità. Alcune sono più complete, per altre i lavori sono ancora in corso. Le funzionalità fornite nelle anteprime includono i tipi riferimento nullable, i criteri di ricerca ricorsivi, i flussi asincroni, intervalli e indici, istruzioni using basate su criteri e dichiarazioni using, assegnazione di unione null.
  
## <a name="related-sections"></a>Sezioni correlate  

 [Guida a C#](../../csharp/index.md)  
 Fornisce un portale per la documentazione di Visual C#.  
  
 [Using the Visual Studio Development Environment for C#](/visualstudio/csharp-ide/using-the-visual-studio-development-environment-for-csharp) (Uso dell'ambiente di sviluppo di Visual Studio per C#)  
 Fornisce i collegamenti ad argomenti relativi a concetti e attività che descrivono IDE e l'editor.  
  
 [Guida per programmatori C#](../../csharp/programming-guide/index.md)  
 Include informazioni su come usare il linguaggio di programmazione C#.
