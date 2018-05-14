---
title: override (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 8f692dfdf8bd34ddb62623d86ec3dadd2b8dead3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="override-c-reference"></a>override (Riferimenti per C#)
Il modificatore `override` è necessario per estendere o modificare l'implementazione astratta o virtuale di un metodo, una proprietà, un indicizzatore o un evento ereditato.  
  
## <a name="example"></a>Esempio  
 In questo esempio la classe `Square` deve specificare un'implementazione sottoposta a override di `Area` poiché `Area` viene ereditato da `ShapesClass` astratto:  
  
 [!code-csharp[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]  
  
 Un metodo `override` offre una nuova implementazione di un membro ereditato da una classe base. Il metodo che viene sottoposto a override mediante una dichiarazione `override` viene definito metodo di base sottoposto a override. Il metodo di base sottoposto a override deve avere la stessa firma del metodo `override`. Per informazioni sull'ereditarietà, vedere [Ereditarietà](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
 Non è possibile eseguire l'override di un metodo non virtuale o statico. Il metodo di base sottoposto a override deve essere `virtual`, `abstract` o `override`.  
  
 Una dichiarazione `override` non può modificare l'accessibilità del metodo `virtual`. Il metodo `override` e il metodo `virtual` devono avere lo stesso [modificatore del livello di accesso](../../../csharp/language-reference/keywords/access-modifiers.md).  
  
 Non è possibile usare i modificatori `new`, `static` o `virtual` per modificare un metodo `override`.  
  
 Una dichiarazione di proprietà di override deve indicare esattamente lo stesso modificatore di accesso, lo stesso tipo e lo stesso nome della proprietà ereditata e la proprietà sottoposta a override deve essere `virtual`, `abstract` o `override`.  
  
 Per altre informazioni sull'uso della parola chiave `override`, vedere [Controllo delle versioni con le parole chiave Override e New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) e [Sapere quando utilizzare le parole chiave Override e New](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).  
  
## <a name="example"></a>Esempio  
 Questo esempio definisce una classe base denominata `Employee` e una classe derivata denominata `SalesEmployee`. La classe `SalesEmployee` include la proprietà aggiuntiva `salesbonus` ed esegue l'override del metodo `CalculatePay` per prenderla in considerazione.  
  
 [!code-csharp[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Ereditarietà](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Modificatori](../../../csharp/language-reference/keywords/modifiers.md)  
 [abstract](../../../csharp/language-reference/keywords/abstract.md)  
 [virtual](../../../csharp/language-reference/keywords/virtual.md)  
 [new](../../../csharp/language-reference/keywords/new.md)  
 [Polimorfismo](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)
