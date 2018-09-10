---
title: Parola chiave explicit (Riferimenti per C#)
ms.date: 08/24/2018
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: 3567a2c5aa549aa3141ed59c3e93e7b07975da70
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525461"
---
# <a name="explicit-c-reference"></a>explicit (Riferimenti per C#)

La parola chiave `explicit` dichiara un operatore di conversione di tipo definito dall'utente che deve essere chiamato con un cast.

L'esempio seguente definisce l'operatore che converte una classe `Fahrenheit` in una classe `Celsius`. L'operatore deve essere definito all'interno una classe `Fahrenheit` o `Celsius`:

[!code-csharp[csrefKeywordsConversion#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#2)]

L'operatore di conversione definito viene richiamato con un cast, come illustrato nell'esempio seguente:

[!code-csharp[csrefKeywordsConversion#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#3)]

L'operatore di conversione converte da un tipo di origine a un tipo di destinazione. Il tipo di origine fornisce l'operatore di conversione. A differenza degli operatori di conversione impliciti, gli operatori di conversione espliciti devono essere chiamati tramite un cast. Se un'operazione di conversione può generare eccezioni o perdita di informazioni, è necessario contrassegnarla come `explicit`. In questo modo si impedisce al compilatore di chiamare automaticamente l'operazione di conversione, con conseguenze imprevedibili.

Se si omette il cast, viene generato l'errore in fase di compilazione CS0266.

Per altre informazioni, vedere [Uso degli operatori di conversione](../../programming-guide/statements-expressions-operators/using-conversion-operators.md).

## <a name="example"></a>Esempio

Nell'esempio seguente vengono fornite una classe `Fahrenheit` e una classe `Celsius`, ognuna delle quali fornisce un operatore di conversione esplicito all'altra classe.

[!code-csharp[csrefKeywordsConversion#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#1)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene definito la struct `Digit`, che rappresenta una singola cifra decimale. Viene definito un operatore per le conversioni da `byte` a `Digit`, tuttavia, poiché non è possibile convertire tutti i byte in `Digit`, la conversione è esplicita.

[!code-csharp[csrefKeywordsConversion#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#4)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)  
- [Guida per programmatori C#](../../programming-guide/index.md)  
- [Parole chiave di C#](index.md)  
- [implicit](implicit.md)  
- [operatore (Riferimenti per C#)](operator.md)  
- [Procedura: Implementare conversioni tra struct definite dall'utente](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
- [Conversioni esplicite concatenate definite dall'utente in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)  
