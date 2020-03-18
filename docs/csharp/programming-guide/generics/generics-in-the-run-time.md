---
title: Generics nel runtime - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], at run time
ms.assetid: 119df7e6-9ceb-49df-af36-24f8f8c0747f
ms.openlocfilehash: a53a21d3028e588f5c4d5ce7bf35fad8d3720a08
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75702987"
---
# <a name="generics-in-the-run-time-c-programming-guide"></a>Generics nel runtime (Guida per programmatori C#)
Quando un tipo o un metodo generico viene compilato in Microsoft Intermediate Language (MSIL), contiene metadati che lo identificano come contenente parametri di tipo. L'uso di MSIL per un tipo generico differisce a seconda che il parametro di tipo sia un tipo valore o un tipo riferimento.  
  
 La prima volta che viene costruito un tipo generico con un tipo valore come parametro, il runtime crea un tipo generico specializzato con il parametro o i parametri specificati sostituiti nelle posizioni appropriate in MSIL. I tipi generici specializzati vengono creati una sola volta per ogni tipo valore univoco usato come parametro.  
  
 Ad esempio, si supponga che il codice programma abbia dichiarato uno stack costituito da interi:  
  
 [!code-csharp[csProgGuideGenerics#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#42)]  
  
 A questo punto, il runtime genera una versione specializzata della classe <xref:System.Collections.Generic.Stack%601> sostituendo l'intero nel modo appropriato per il parametro. D'ora in poi, ogni volta che il codice programma usa uno stack di interi, il runtime riutilizzerà la classe <xref:System.Collections.Generic.Stack%601> specializzata generata. Nell'esempio seguente vengono create due istanze di uno stack di interi che condividono un'istanza singola nel codice `Stack<int>`:  
  
 [!code-csharp[csProgGuideGenerics#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#43)]  
  
 Tuttavia, si supponga che venga creata un'altra classe <xref:System.Collections.Generic.Stack%601> con un tipo valore diverso, ad esempio `long`, o una struttura definita dall'utente come parametro in un altro punto del codice. Di conseguenza, il runtime genererà un'altra versione del tipo generico e sostituirà un valore `long` nelle posizioni appropriate in MSIL. Le conversioni non sono più necessarie, perché ogni classe generica specializzata contiene il tipo valore in modo nativo.  
  
 I generics hanno un funzionamento leggermente diverso con i tipi riferimento. La prima volta che viene costruito un tipo generico con qualsiasi tipo riferimento, il runtime crea un tipo generico specializzato con riferimenti a oggetti sostituiti per i parametri in MSIL. Quindi, ogni volta che viene creata un'istanza di un tipo costruito con un tipo riferimento come parametro, indipendentemente dal tipo, il runtime riutilizza la versione specializzata precedentemente creata del tipo generico. Questo è possibile perché tutti i riferimenti hanno le stesse dimensioni.  
  
 Ad esempio, si supponga di avere due tipi riferimento, una classe `Customer` e una classe `Order`, e di aver creato uno stack di tipi `Customer`:  
  
 [!code-csharp[csProgGuideGenerics#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#47)]  
  
 [!code-csharp[csProgGuideGenerics#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#44)]  
  
 A questo punto, il runtime genera una versione specializzata della classe <xref:System.Collections.Generic.Stack%601> in cui sono archiviati riferimenti a oggetti che verranno compilati successivamente invece di archiviare i dati. Si supponga che la riga di codice successiva crei uno stack di un altro tipo riferimento, chiamato `Order`:  
  
 [!code-csharp[csProgGuideGenerics#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#45)]  
  
 Diversamente dai tipi valore, non viene creata un'altra versione specializzata della classe <xref:System.Collections.Generic.Stack%601> per il tipo `Order`. Viene invece creata un'istanza della versione specializzata della classe <xref:System.Collections.Generic.Stack%601> e viene impostata la variabile `orders` per referenziarla. Si supponga di individuare una riga di codice per la creazione di uno stack di un tipo `Customer`:  
  
 [!code-csharp[csProgGuideGenerics#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#46)]  
  
 Come per l'uso precedente della classe <xref:System.Collections.Generic.Stack%601> creata con il tipo `Order`, verrà creata un'altra istanza della classe <xref:System.Collections.Generic.Stack%601> specializzata. I puntatori contenuti vengono impostati in modo da fare riferimento a un'area di memoria delle dimensioni di un tipo `Customer`. Poiché il numero di tipi riferimento può variare ampiamente a seconda del programma, l'implementazione C# di generics riduce notevolmente la quantità di codice limitando a uno il numero di classi specializzate create dal compilatore per classi generiche di tipi riferimento.  
  
 Inoltre, quando viene creata un'istanza di una classe C# generica usando un tipo valore o un parametro di tipo riferimento, la reflection può eseguire query sulla classe, accertandone il tipo effettivo e il parametro di tipo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic>
- [Guida per programmatori C#](../index.md)
- [Introduzione ai generics](./index.md)
- [Generics](../../../standard/generics/index.md)
