---
title: Suggerimenti sulle prestazioni .NET
ms.date: 03/30/2017
helpviewer_keywords:
- C# language, performance
- performance [C#]
- Visual Basic, performance
- performance [Visual Basic]
ms.assetid: ae275793-857d-4102-9095-b4c2a02d57f4
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d5d91db9256cdfb3aa0062d66333f13797ee1bb
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47078565"
---
# <a name="net-performance-tips"></a>Suggerimenti sulle prestazioni .NET
Il termine *prestazioni* si riferisce in genere alla velocità di esecuzione di un programma. In alcuni casi, è possibile aumentare la velocità di esecuzione seguendo determinate regole di base nel codice sorgente. In alcuni programmi, è importante esaminare attentamente il codice e usare i profiler per verificare che venga eseguito il più velocemente possibile. In altri programmi, non è necessario eseguire questa ottimizzazione perché il codice viene eseguito con una velocità ragionevole così com'è scritto. In questo articolo sono elencate alcune aree in cui si verificano comunemente problemi di prestazioni e vengono proposti suggerimenti per migliorarle, oltre a collegamenti ad altri argomenti dedicati alle prestazioni. Per altre informazioni sulla pianificazione e la misurazione delle prestazioni, vedere [Prestazioni](../../../docs/framework/performance/index.md)  
  
## <a name="boxing-and-unboxing"></a>Boxing e unboxing  
 È consigliabile evitare l'uso di tipi valore nelle situazioni in cui devono essere sottoposti a conversione boxing un numero elevato di volte, ad esempio nelle classi di raccolte non generiche, come <xref:System.Collections.ArrayList?displayProperty=nameWithType>. È possibile evitare la conversione boxing di tipi valore usando raccolte generiche, come <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>. Le conversioni boxing e unboxing sono processi onerosi dal punto di vista del calcolo. Quando un tipo valore viene sottoposto a conversione boxing, è necessario creare un oggetto completamente nuovo. L'operazione può richiedere fino a 20 volte più tempo rispetto a una semplice assegnazione di riferimento. Durante l'unboxing, il processo di cast può richiedere il quadruplo del tempo rispetto a un'assegnazione. Per altre informazioni, vedere [Boxing e unboxing](~/docs/csharp/programming-guide/types/boxing-and-unboxing.md).  
  
## <a name="strings"></a>Stringhe  
 Quando si concatena un numero elevato di variabili stringa, ad esempio in un ciclo rigido, usare <xref:System.Text.StringBuilder?displayProperty=nameWithType> invece dell'[operatore +](~/docs/csharp/language-reference/operators/addition-operator.md) C# o degli [operatori di concatenazione](~/docs/visual-basic/language-reference/operators/concatenation-operators.md) di Visual Basic. Per altre informazioni, vedere [Procedura: Concatenare più stringhe](../../csharp/how-to/concatenate-multiple-strings.md) e [Operatori di concatenazione in Visual Basic](~/docs/visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md).  
  
## <a name="destructors"></a>Distruttori  
 Non usare distruttori vuoti. Quando una classe contiene un distruttore, viene creata una voce nella coda Finalize. Quando si chiama il distruttore, viene richiamato Garbage Collector per elaborare la coda. Se il distruttore è vuoto, si verifica semplicemente un calo di prestazioni. Per altre informazioni, vedere [Distruttori](~/docs/csharp/programming-guide/classes-and-structs/destructors.md) e [Durata degli oggetti: come creare ed eliminare definitivamente oggetti](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
## <a name="other-resources"></a>Altre risorse  
  
-   [Writing Faster Managed Code: Know What Things Cost](https://go.microsoft.com/fwlink/?LinkId=99294) (Scrittura di codice gestito più veloce: essere consapevoli dei costi)  
  
-   [Writing High-Performance Managed Applications: A Primer](https://go.microsoft.com/fwlink/?LinkId=99295) (Scrittura di applicazioni gestite ad alte prestazioni: guida di base)  
  
-   [Garbage Collector Basics and Performance Hints](https://go.microsoft.com/fwlink/?LinkId=99296) (Concetti di base di Garbage Collector e suggerimenti per le prestazioni)  
  
-   [Performance Tips and Tricks in .NET Applications](https://go.microsoft.com/fwlink/?LinkId=99297) (Suggerimenti e trucchi per le prestazioni nelle applicazioni .NET)  

-   [Rico Mariani's Performance Tidbits](https://go.microsoft.com/fwlink/?LinkId=115679) (Suggerimenti per le prestazioni di Rico Mariani)  

-   [Blog di Vance](https://blogs.msdn.microsoft.com/vancem/)
  
## <a name="see-also"></a>Vedere anche  
 [Prestazioni](../../../docs/framework/performance/index.md)  
 [Nozioni di base sulla programmazione](https://msdn.microsoft.com/library/65c12cca-af4f-4017-886e-2dbc00a189d6)  
 [Guida per programmatori Visual Basic](../../visual-basic/programming-guide/index.md)  
 [Guida per programmatori C#](https://msdn.microsoft.com/library/ac0f23a2-6bf3-4077-be99-538ae5fd3bc5)
