---
title: Informazioni di riferimento su C#
ms.date: 02/14/2017
helpviewer_keywords:
- Visual C#, language reference
- language reference [C#]
- Programmer's Reference for C#
- C# language, reference
- reference, C# language
ms.assetid: 06de3167-c16c-4e1a-b3c5-c27841d4569a
ms.openlocfilehash: 4875e53327e24c4b5983a4a3b79b5beced368725
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74428612"
---
# <a name="c-reference"></a>Informazioni di riferimento su C#

Questa sezione offre informazioni di riferimento su parole chiave, operatori, caratteri speciali, direttive del preprocessore, opzioni del compilatore ed errori e avvisi del compilatore in C#.  
  
## <a name="in-this-section"></a>Contenuto della sezione

 [Parole chiave di C#](./keywords/index.md)  
 Fornisce collegamenti a informazioni su sintassi e parole chiave di C#.  
  
 [Operatori di C](./operators/index.md)  
 Fornisce collegamenti a informazioni su sintassi e operatori di C#.  

 [Caratteri speciali di C#](./tokens/index.md)  
 Fornisce collegamenti a informazioni sui caratteri speciali contestuali di C# e sul relativo utilizzo.  

 [Direttive per il preprocessore di C](./preprocessor-directives/index.md)  
 Fornisce collegamenti a informazioni sui comandi del compilatore per l'incorporamento nel codice sorgente C#.  
  
 [Opzioni del compilatore C](./compiler-options/index.md)  
 Include informazioni sulle opzioni del compilatore e su come usarle.  
  
 [Errori del compilatore C#](./compiler-messages/index.md)  
 Include frammenti di codice che illustrano la causa e la correzione per gli errori del compilatore e gli avvisi di C#.  
  
 [Specifiche del linguaggio C#](../../../_csharplang/spec/introduction.md)  
 Specifica del linguaggio C# 6.0. Si tratta di una proposta bozza per il linguaggio C# 6.0. Questo documento verrà perfezionato attraverso il lavoro con il comitato per gli standard ECMA c.. La versione 5.0 è stata rilasciata a dicembre 2017 come documento [Standard ECMA-334 5th Edition](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf).

Le funzionalità che sono state implementate nelle versioni di C# successive alla 6.0 sono rappresentate in proposte di specifica del linguaggio. Questi documenti descrivono i progetti per la specifica del linguaggio per l'aggiunta di queste nuove funzionalità. Questi sono in progetto di proposta. Queste specifiche saranno perfezionate e presentate al comitato per gli standard ECMA per la revisione formale e l'incorporazione in una versione futura dello standard C.

 [Proposte di specifiche di C.7.0](../../../_csharplang/proposals/csharp-7.0/pattern-matching.md)  
 Esistono varie nuove funzionalità implementate in C# 7.0, tra le quali criteri di ricerca, funzioni locali, dichiarazioni di variabili out, espressioni throw, valori letterali binari e separatori di cifre. Questa cartella contiene le specifiche per ognuna di tali funzionalità.
  
 [Proposte di specifiche di C.1](../../../_csharplang/proposals/csharp-7.1/async-main.md)  
 In C# 7.1 sono state aggiunte nuove funzionalità. Prima di tutto, è possibile scrivere un metodo `Main` che restituisce `Task` o `Task<int>`. In questo modo è possibile aggiungere il modificatore `async` a `Main`. L'espressione `default` può essere usata senza un tipo nelle posizioni in cui il tipo può essere dedotto. Possono essere dedotti anche i nomi dei membri delle tuple. Infine, è possibile usare criteri di ricerca con generics.

 [Proposte di specifiche di C.2](../../../_csharplang/proposals/csharp-7.2/readonly-ref.md)  
 In C# 7.2 sono state aggiunte varie piccole funzionalità. È possibile passare argomenti per riferimento di sola lettura tramite la parola chiave `in`. Sono state introdotte numerose modifiche di basso livello per supportare la sicurezza in fase di compilazione per `Span` e i tipi correlati. È possibile usare argomenti denominati in cui gli argomenti successivi sono posizionali, in alcune situazioni. Il modificatore di accesso `private protected` consente di specificare che i chiamanti sono limitati ai tipi derivati implementati nello stesso assembly. L' operatore `?:` può essere risolto come riferimento a una variabile. È anche possibile formattare i numeri esadecimali e binari usando un separatore di cifra iniziale.

 [Proposte di specifiche di C.3](../../../_csharplang/proposals/csharp-7.3/blittable.md)  
 C# 7.3 è un'altra versione secondaria che include numerosi piccoli aggiornamenti. È possibile usare nuovi vincoli per i parametri di tipo generico. Altre modifiche semplificano l'utilizzo `fixed` dei [`stackalloc`](./operators/stackalloc.md) campi, incluso l'utilizzo delle allocazioni. Le variabili locali `ref` dichiarate con la parola chiave possono essere riassegnate per fare riferimento a una nuova risorsa di archiviazione. È possibile posizionare attributi in proprietà implementate automaticamente destinate al campo di supporto generato dal compilatore. È possibile usare variabili di espressione negli inizializzatori. Le tuple possono essere confrontate per verificarne l'uguaglianza (o la disuguaglianza). Sono stati introdotti anche alcuni miglioramenti per la risoluzione dell'overload.
  
 [Proposte di specifiche di C.8.0](../../../_csharplang/proposals/csharp-8.0/nullable-reference-types.md)  
 La versione 8.0 di Cè è disponibile con .NET Core 3.0. Le funzionalità includono tipi di riferimento nullable, criteri di ricerca ricorsivi, metodi di interfaccia predefiniti, flussi asincroni, intervalli e indici, basato su modelli utilizzando e utilizzando dichiarazioni, assegnazione null coalescing e membri di istanza di sola lettura.
  
## <a name="related-sections"></a>Sezioni correlate  

 [Uso dell'ambiente di sviluppo di Visual Studio per C#](/visualstudio/get-started/csharp)  
 Fornisce i collegamenti ad argomenti relativi a concetti e attività che descrivono IDE e l'editor.  
  
 [Guida per programmatori C#](../programming-guide/index.md)  
 Include informazioni su come usare il linguaggio di programmazione C#.
