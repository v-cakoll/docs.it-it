---
title: explicit (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: c8a05aef3318eb34242ed1268ea26663592e4d1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="explicit-c-reference"></a>explicit (Riferimenti per C#)
La parola chiave `explicit` dichiara un operatore di conversione di tipo definito dall'utente che deve essere chiamato con un cast. Questo operatore, ad esempio, esegue la conversione da una classe chiamata Fahrenheit a una classe chiamata Celsius:  
  
 [!code-csharp[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]  
  
 L'operatore di conversione può essere chiamato come segue:  
  
 [!code-csharp[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]  
  
 L'operatore di conversione converte da un tipo di origine a un tipo di destinazione. Il tipo di origine fornisce l'operatore di conversione. A differenza degli operatori di conversione impliciti, gli operatori di conversione espliciti devono essere chiamati tramite un cast. Se un'operazione di conversione può generare eccezioni o perdita di informazioni, è necessario contrassegnarla come `explicit`. In questo modo si impedisce al compilatore di chiamare automaticamente l'operazione di conversione, con conseguenze imprevedibili.  
  
 Se si omette il cast, viene generato l'errore in fase di compilazione CS0266.  
  
 Per altre informazioni, vedere [Uso degli operatori di conversione](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono fornite una classe `Fahrenheit` e una classe `Celsius`, ognuna delle quali fornisce un operatore di conversione esplicito all'altra classe.  
  
 [!code-csharp[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definito la struct `Digit`, che rappresenta una singola cifra decimale. Viene definito un operatore per le conversioni da `byte` a `Digit`, tuttavia, poiché non è possibile convertire tutti i byte in `Digit`, la conversione è esplicita.  
  
 [!code-csharp[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [implicit](../../../csharp/language-reference/keywords/implicit.md)  
 [operatore (Riferimenti per C#)](../../../csharp/language-reference/keywords/operator.md)  
 [Procedura: Implementare conversioni tra struct definite dall'utente](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
 [Conversioni esplicite concatenate definite dall'utente in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
