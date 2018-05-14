---
title: while (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: 23c5ca3bb7dc401a894a6c3918fbaec9a9306153
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="while-c-reference"></a>while (Riferimenti per C#)
L'istruzione `while` esegue un'istruzione o un blocco di istruzioni finché un'espressione specificata non restituisce `false`.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a>Esempio  
 Poiché il test dell'espressione `while` viene eseguito prima di ogni esecuzione del ciclo, un ciclo `while` viene eseguito zero o più volte. Questo comportamento è diverso dal ciclo [do](../../../csharp/language-reference/keywords/do.md), che viene eseguito una o più volte.  
  
 Un ciclo `while` può essere terminato quando un'istruzione [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md) trasferisce il controllo all'esterno del ciclo. Per passare il controllo all'iterazione successiva senza uscire dal ciclo, usare l'istruzione [continue](../../../csharp/language-reference/keywords/continue.md). Si noti la differenza di output nei tre esempi precedenti, a seconda di dove `int n` viene incrementato. Nell'esempio seguente non viene generato alcun output.  
  
 [!code-csharp[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Istruzione while (C++)](/cpp/cpp/while-statement-cpp)  
 [Istruzioni di iterazione](../../../csharp/language-reference/keywords/iteration-statements.md)
