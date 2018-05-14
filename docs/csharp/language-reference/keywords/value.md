---
title: value (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: c8f808540385552f6222566f23251f6cbd6e86df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="value-c-reference"></a>value (Riferimenti per C#)
La parola chiave contestuale `value` viene usata nella funzione di accesso set nelle dichiarazioni di proprietà ordinarie. È simile a un parametro di input su un metodo. La parola `value` fa riferimento al valore che il codice client tenta di assegnare alla proprietà. Nell'esempio seguente, `MyDerivedClass` ha una proprietà denominata `Name` che usa il parametro `value` per assegnare una nuova stringa al campo sottostante `name`. Dal punto di vista del codice client, l'operazione viene scritta come assegnazione semplice.  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]  
  
 Per altre informazioni sull'uso di `value`, vedere [Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md).  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)
