---
title: foreach, in (Riferimenti per C#)
ms.date: 10/11/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: "29"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d5601682d53a01ff07aba7e416aa81ded4c03e4e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="foreach-in-c-reference"></a>foreach, in (Riferimenti per C#)
L'istruzione `foreach` ripete un gruppo di istruzioni incorporate per ciascun elemento di una matrice o di una raccolta di oggetti che implementa l'interfaccia <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. L'istruzione `foreach` viene usata per eseguire l'iterazione della raccolta e ottenere le informazioni desiderate. Per evitare effetti indesiderati, non deve tuttavia essere usata per aggiungere o rimuovere elementi dalla raccolta di origine. Se è necessario aggiungere o rimuovere elementi dalla raccolta di origine, usare il ciclo [for](for.md).
  
 L'esecuzione delle istruzioni incorporate viene ripetuta per ogni elemento nella matrice o nella raccolta. Quando l'iterazione è stata completata per tutti gli elementi nella raccolta, il controllo viene trasferito alla prima istruzione che segue il blocco `foreach`.
  
 In un punto qualsiasi all'interno del blocco `foreach` è possibile uscire dal ciclo usando la parola chiave [break](break.md) o passare all'iterazione successiva nel ciclo con la parola chiave [continue](continue.md).

 È anche possibile uscire da un ciclo `foreach` tramite le istruzioni [goto](goto.md), [return](return.md) o [throw](throw.md).

 Per altre informazioni sulla parola chiave `foreach` e per esempi di codice, vedere gli argomenti riportati di seguito:  

 [Uso di foreach con matrici](../../programming-guide/arrays/using-foreach-with-arrays.md)  

 [Procedura: Accedere a una classe Collection con foreach](../../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  

## <a name="example"></a>Esempio
 Il codice seguente mostra tre esempi.

> [!TIP]
> È possibile modificare gli esempi per sperimentare con la sintassi e utilizzi diversi di più simili al caso di utilizzo. Premere "Esegui" per eseguire il codice, quindi modificare e premere "Esegui".

-   Un ciclo `foreach` tipico che visualizza il contenuto di una matrice di numeri interi

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L12-L26)]

-   Un ciclo [for](../../../csharp/language-reference/keywords/for.md) che esegue la stessa operazione

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L31-L46)]

-   Un ciclo `foreach` che gestisce un conteggio del numero di elementi nella matrice

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L51-L69)]
 
## <a name="c-language-specification"></a>Specifiche del linguaggio C#
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche  

[Riferimenti per C#](../index.md)

[Guida per programmatori C#](../../programming-guide/index.md)

[Parole chiave di C#](index.md)

[Istruzioni di iterazione](iteration-statements.md)

[for](for.md)
