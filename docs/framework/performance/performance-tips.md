---
title: Suggerimenti sulle prestazioni .NET
description: Esplorare i suggerimenti sulle prestazioni per migliorare la velocità di esecuzione di un programma in .NET. Vedere Suggerimenti per la conversione boxing e unboxing, le stringhe e i distruttori.
ms.date: 03/30/2017
helpviewer_keywords:
- C# language, performance
- performance [C#]
- Visual Basic, performance
- performance [Visual Basic]
ms.assetid: ae275793-857d-4102-9095-b4c2a02d57f4
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2b3be8b42b5046e52074236de01ca312a0a9a361
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474267"
---
# <a name="net-performance-tips"></a>Suggerimenti sulle prestazioni .NET
Il termine *prestazioni* si riferisce in genere alla velocità di esecuzione di un programma. In alcuni casi, è possibile aumentare la velocità di esecuzione seguendo determinate regole di base nel codice sorgente. In alcuni programmi, è importante esaminare attentamente il codice e usare i profiler per verificare che venga eseguito il più velocemente possibile. In altri programmi, non è necessario eseguire questa ottimizzazione perché il codice viene eseguito con una velocità ragionevole così com'è scritto. In questo articolo sono elencate alcune aree in cui si verificano comunemente problemi di prestazioni e vengono proposti suggerimenti per migliorarle, oltre a collegamenti ad altri argomenti dedicati alle prestazioni. Per altre informazioni sulla pianificazione e la misurazione delle prestazioni, vedere [Prestazioni](index.md)  
  
## <a name="boxing-and-unboxing"></a>Boxing e unboxing  
 È consigliabile evitare l'uso di tipi valore nelle situazioni in cui devono essere sottoposti a conversione boxing un numero elevato di volte, ad esempio nelle classi di raccolte non generiche, come <xref:System.Collections.ArrayList?displayProperty=nameWithType>. È possibile evitare la conversione boxing di tipi valore usando raccolte generiche, come <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>. Le conversioni boxing e unboxing sono processi onerosi dal punto di vista del calcolo. Quando un tipo valore viene sottoposto a conversione boxing, è necessario creare un oggetto completamente nuovo. L'operazione può richiedere fino a 20 volte più tempo rispetto a una semplice assegnazione di riferimento. Durante l'unboxing, il processo di cast può richiedere il quadruplo del tempo rispetto a un'assegnazione. Per altre informazioni, vedere [Boxing e unboxing](../../csharp/programming-guide/types/boxing-and-unboxing.md).  
  
## <a name="strings"></a>Stringhe  
 Quando si concatena un numero elevato di variabili stringa, ad esempio in un ciclo rigido, usare <xref:System.Text.StringBuilder?displayProperty=nameWithType> invece dell'[operatore +](../../csharp/language-reference/operators/addition-operator.md) C# o degli [operatori di concatenazione](../../visual-basic/language-reference/operators/concatenation-operators.md) di Visual Basic. Per ulteriori informazioni, vedere [come concatenare più stringhe](../../csharp/how-to/concatenate-multiple-strings.md) e [operatori di concatenazione in Visual Basic](../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md).  
  
## <a name="destructors"></a>Distruttori  
 Non usare distruttori vuoti. Quando una classe contiene un distruttore, viene creata una voce nella coda Finalize. Quando si chiama il distruttore, viene richiamato Garbage Collector per elaborare la coda. Se il distruttore è vuoto, si verifica semplicemente un calo di prestazioni. Per altre informazioni, vedere [Distruttori](../../csharp/programming-guide/classes-and-structs/destructors.md) e [Durata degli oggetti: come creare ed eliminare definitivamente oggetti](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
## <a name="other-resources"></a>Risorse aggiuntive  
  
- [Writing Faster Managed Code: Know What Things Cost](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973852(v=msdn.10)) (Scrittura di codice gestito più veloce: essere consapevoli dei costi)  
  
- [Writing High-Performance Managed Applications: A Primer](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973858(v=msdn.10)) (Scrittura di applicazioni gestite ad alte prestazioni: guida di base)  
  
- [Garbage Collector Basics and Performance Hints](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973837(v=msdn.10)) (Concetti di base di Garbage Collector e suggerimenti per le prestazioni)  
  
- [Performance Tips and Tricks in .NET Applications](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973839(v=msdn.10)) (Suggerimenti e trucchi per le prestazioni nelle applicazioni .NET)  

- [Rico Mariani's Performance Tidbits](https://docs.microsoft.com/archive/blogs/ricom/) (Suggerimenti per le prestazioni di Rico Mariani)  

- [Blog di Vance Morrison](https://docs.microsoft.com/archive/blogs/vancem/)
  
## <a name="see-also"></a>Vedere anche

- [Prestazioni](index.md)
- [Guida per programmatori Visual Basic](../../visual-basic/programming-guide/index.md)
- [Guida per programmatori C#](../../csharp/programming-guide/index.md)
