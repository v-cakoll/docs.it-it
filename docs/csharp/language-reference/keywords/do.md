---
title: do (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 5599f079e29fd094c4d6a6a75afba89fb562a166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="do-c-reference"></a>do (Riferimenti per C#)
L'istruzione `do` esegue ripetutamente un'istruzione o un blocco di istruzioni finché un'espressione specificata non restituisce `false`. Il corpo del ciclo deve essere racchiuso tra parentesi graffe, `{}`, a meno che sia costituito da una singola istruzione. In tal caso le parentesi graffe sono facoltative.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono eseguite le istruzioni del ciclo `do-while` fino a quando la variabile `x` è minore di 5.  
  
 [!code-csharp[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 A differenza dell'istruzione [while](../../../csharp/language-reference/keywords/while.md), un ciclo `do-while` viene eseguito una sola volta prima che sia valutata l'espressione condizionale.  
  
 In qualsiasi momento nel blocco `do-while` è possibile uscire dal ciclo usando l'istruzione [break](../../../csharp/language-reference/keywords/break.md). Si può eseguire direttamente l'istruzione di valutazione dell'espressione `while` usando l'istruzione [continue](../../../csharp/language-reference/keywords/continue.md). Se l'espressione `while` restituisce true, l'esecuzione continua con la prima istruzione del ciclo. Se l'espressione restituisce false, l'esecuzione continua con la prima istruzione dopo il ciclo `do-while`.  
  
 È possibile uscire da un ciclo `do-while` anche con le istruzioni [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Istruzione do-while (C++)](/cpp/cpp/do-while-statement-cpp)  
 [Istruzioni di iterazione](../../../csharp/language-reference/keywords/iteration-statements.md)
