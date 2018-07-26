---
title: foreach, in (Riferimenti per C#)
ms.date: 06/29/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: a6397cdc9d1e36423a14158a57ca2c1b3fe9df17
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874962"
---
# <a name="foreach-in-c-reference"></a>foreach, in (Riferimenti per C#)

L'istruzione `foreach` esegue un'istruzione o un blocco di istruzioni per ogni elemento in un'istanza del tipo che implementa l'interfaccia <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. L'istruzione `foreach` non è limitata a questi tipi e può essere applicata a un'istanza di qualsiasi tipo che soddisfa le condizioni seguenti:

- include il metodo `GetEnumerator` pubblico senza parametri con tipo restituito classe, struct o interfaccia,
- il tipo restituito del metodo `GetEnumerator` include la proprietà `Current` pubblica e il metodo `MoveNext` pubblico senza parametri con tipo restituito <xref:System.Boolean>.

In un punto qualsiasi all'interno del blocco dell'istruzione `foreach` è possibile uscire dal ciclo usando l'istruzione [break](break.md) o passare all'iterazione successiva nel ciclo con l'istruzione [continue](continue.md). Si può uscire da un ciclo `foreach` anche usando l'istruzione [goto](goto.md), [return](return.md) o [throw](throw.md).

## <a name="examples"></a>Esempi

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

L'esempio seguente mostra l'utilizzo dell'istruzione `foreach` con un'istanza del tipo <xref:System.Collections.Generic.List%601> che implementa l'interfaccia <xref:System.Collections.Generic.IEnumerable%601>:

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

L'esempio successivo usa l'istruzione `foreach` con un'istanza del tipo <xref:System.Span%601?displayProperty=nameWithType>, che non implementa alcuna interfaccia:

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

A partire da C# 7.3, se la proprietà `Current` dell'enumeratore restituisce un [valore restituito di riferimento](../../programming-guide/classes-and-structs/ref-returns.md) (`ref T` dove `T` è il tipo dell'elemento della raccolta), è possibile dichiarare la variabile di iterazione con il modificatore `ref` o `ref readonly`. L'esempio seguente usa una variabile di iterazione `ref` per impostare il valore di ogni elemento in una matrice di stackalloc. La versione `ref readonly` esegue l'iterazione della raccolta per stampare tutti i valori. La dichiarazione `readonly` usa una dichiarazione di variabile locale implicita. Le dichiarazioni di variabili implicite possono essere usate con le dichiarazioni `ref` o `ref readonly`, così come le dichiarazioni di variabili tipizzate.

[!code-csharp-interactive[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

[Istruzione foreach (specifica del linguaggio C#)](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)  
[Uso di foreach con matrici](../../programming-guide/arrays/using-foreach-with-arrays.md)  
[for](for.md)  
[Istruzioni di iterazione](iteration-statements.md)  
[Parole chiave di C#](index.md)  
[Riferimenti per C#](../index.md)  
[Guida per programmatori C#](../../programming-guide/index.md)  
