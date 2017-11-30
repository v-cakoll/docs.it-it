---
title: return (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 90c84b51c6ee57864eac552bc488c9f9c15e9394
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="return-c-reference"></a>return (Riferimenti per C#)
L'istruzione `return` termina l'esecuzione del metodo in cui viene visualizzata e restituisce il controllo al metodo di chiamata. Può restituire anche un valore facoltativo. Se il metodo è un tipo `void`, l'istruzione `return` può essere omessa.  
  
 Se l'istruzione return è all'interno di un blocco `try`, il blocco `finally`, se presente, verrà eseguito prima che il controllo venga restituito al metodo di chiamata.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, il metodo `CalculateArea()` restituisce la variabile locale `area` come un [doppie](../../../csharp/language-reference/keywords/double.md) valore.  
  
 [!code-csharp[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Istruzione return](/cpp/cpp/return-statement-cpp)  
 [Istruzioni di spostamento](../../../csharp/language-reference/keywords/jump-statements.md)
