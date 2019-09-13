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
ms.openlocfilehash: fd5c39bfcb05296a36d94ea64946f8c29ed7e4d6
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70925349"
---
# <a name="c-reference"></a>Riferimenti per C#
Questa sezione offre informazioni di riferimento su parole chiave, operatori, caratteri speciali, direttive del preprocessore, opzioni del compilatore ed errori e avvisi del compilatore in C#.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Parole chiave di C#](./keywords/index.md)  
 Fornisce collegamenti a informazioni su sintassi e parole chiave di C#.  
  
 [Operatori C#](./operators/index.md)  
 Fornisce collegamenti a informazioni su sintassi e operatori di C#.  

 [Caratteri speciali di C#](./tokens/index.md)  
 Fornisce collegamenti a informazioni sui caratteri speciali contestuali di C# e sul relativo utilizzo.  

 [Direttive per il preprocessore C#](./preprocessor-directives/index.md)  
 Fornisce collegamenti a informazioni sui comandi del compilatore per l'incorporamento nel codice sorgente C#.  
  
 [Opzioni del compilatore C#](./compiler-options/index.md)  
 Include informazioni sulle opzioni del compilatore e su come usarle.  
  
 [Errori del compilatore C#](./compiler-messages/index.md)  
 Include frammenti di codice che illustrano la causa e la correzione per gli errori del compilatore e gli avvisi di C#.  
  
 [Specifiche del linguaggio C#](../../../_csharplang/spec/introduction.md)  
 Specifica del linguaggio C# 6.0. Si tratta di una proposta bozza per il linguaggio C# 6.0. Questo documento verrà perfezionato tramite l'utilizzo del Comitato C# degli standard ECMA. La versione 5.0 è stata rilasciata a dicembre 2017 come documento [Standard ECMA-334 5th Edition](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf).

Le funzionalità che sono state implementate nelle versioni di C# successive alla 6.0 sono rappresentate in proposte di specifica del linguaggio. Questi documenti descrivono i progetti per la specifica del linguaggio per l'aggiunta di queste nuove funzionalità. Si trovano nel modulo bozza proposta. Queste specifiche verranno perfezionate e inviate al Comitato degli standard ECMA per la revisione formale e l' C# integrazione in una versione futura dello standard.

 [C#7,0 proposte specifiche](../../../_csharplang/proposals/csharp-7.0/pattern-matching.md)  
 Esistono varie nuove funzionalità implementate in C# 7.0, tra le quali criteri di ricerca, funzioni locali, dichiarazioni di variabili out, espressioni throw, valori letterali binari e separatori di cifre. Questa cartella contiene le specifiche per ognuna di tali funzionalità.
  
 [C#7,1 proposte specifiche](../../../_csharplang/proposals/csharp-7.1/async-main.md)  
 In C# 7.1 sono state aggiunte nuove funzionalità. Prima di tutto, è possibile scrivere un metodo `Main` che restituisce `Task` o `Task<int>`. In questo modo è possibile aggiungere il modificatore `async` a `Main`. L'espressione `default` può essere usata senza un tipo nelle posizioni in cui il tipo può essere dedotto. Possono essere dedotti anche i nomi dei membri delle tuple. Infine, è possibile usare criteri di ricerca con generics.

 [C#7,2 proposte specifiche](../../../_csharplang/proposals/csharp-7.2/readonly-ref.md)  
 In C# 7.2 sono state aggiunte varie piccole funzionalità. È possibile passare argomenti per riferimento di sola lettura tramite la parola chiave `in`. Sono state introdotte numerose modifiche di basso livello per supportare la sicurezza in fase di compilazione per `Span` e i tipi correlati. È possibile usare argomenti denominati in cui gli argomenti successivi sono posizionali, in alcune situazioni. Il modificatore di accesso `private protected` consente di specificare che i chiamanti sono limitati ai tipi derivati implementati nello stesso assembly. L' operatore `?:` può essere risolto come riferimento a una variabile. È anche possibile formattare i numeri esadecimali e binari usando un separatore di cifra iniziale.

 [C#7,3 proposte specifiche](../../../_csharplang/proposals/csharp-7.3/blittable.md)  
 C# 7.3 è un'altra versione secondaria che include numerosi piccoli aggiornamenti. È possibile usare nuovi vincoli per i parametri di tipo generico. Altre modifiche rendono più facile lavorare con i campi `fixed`, incluso l'uso delle allocazioni [`stackalloc`](./operators/stackalloc.md). Le variabili locali dichiarate con la parola chiave `ref` potrebbero essere riassegnate per fare riferimento alla nuova risorsa di archiviazione. È possibile posizionare attributi in proprietà implementate automaticamente destinate al campo di supporto generato dal compilatore. È possibile usare variabili di espressione negli inizializzatori. Le tuple possono essere confrontate per verificarne l'uguaglianza (o la disuguaglianza). Sono stati introdotti anche alcuni miglioramenti per la risoluzione dell'overload.
  
 [C#8,0 proposte specifiche](../../../_csharplang/proposals/csharp-8.0/nullable-reference-types.md)  
 C#8,0 è disponibile con .NET Core 3,0. Le funzionalità includono i tipi di riferimento Nullable, i criteri di ricerca ricorsivi, i membri dell'interfaccia predefiniti, i flussi asincroni, gli intervalli e gli indici, il modello basato sull'utilizzo di dichiarazioni, l'assegnazione di Unione null e i membri dell'istanza di ReadOnly.
  
## <a name="related-sections"></a>Sezioni correlate  

 [Guida a C#](../index.md)  
 Fornisce un portale per la documentazione di Visual C#.  
  
 [Using the Visual Studio Development Environment for C#](/visualstudio/get-started/csharp) (Uso dell'ambiente di sviluppo di Visual Studio per C#)  
 Fornisce i collegamenti ad argomenti relativi a concetti e attività che descrivono IDE e l'editor.  
  
 [Guida per programmatori C#](../programming-guide/index.md)  
 Include informazioni su come usare il linguaggio di programmazione C#.
