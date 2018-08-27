---
title: public (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 853f9c9ebe36345a897337d4e793d3c88059e068
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "42998727"
---
# <a name="public-c-reference"></a>public (Riferimenti per C#)
La parola chiave `public` è un modificatore di accesso per tipi e membri dei tipi. L'accesso pubblico è il livello di accesso più permissivo. Non esistono restrizioni per i membri dell'accesso pubblico, come nel seguente esempio:  
  
```csharp  
class SampleClass  
{  
    public int x; // No access restrictions.  
}  
```  
  
 Per altre informazioni, vedere [Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) e [Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono dichiarate due classi, `PointTest` e `MainClass`. I membri pubblici `x` e `y` di `PointTest` sono accessibili direttamente da `MainClass`.  
  
 [!code-csharp[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/public_1.cs)]  
  
 Se si modifica il livello di accesso `public` impostandolo su [private](../../../csharp/language-reference/keywords/private.md) o [protected](../../../csharp/language-reference/keywords/protected.md), viene visualizzato un messaggio di errore che  
  
 indica che PointTest.y è inaccessibile a causa del livello di protezione.  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
- [Modificatori di accesso](../../../csharp/language-reference/keywords/access-modifiers.md)  
- [Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md)  
- [Modificatori](../../../csharp/language-reference/keywords/modifiers.md)  
- [private](../../../csharp/language-reference/keywords/private.md)  
- [protected](../../../csharp/language-reference/keywords/protected.md)  
- [internal](../../../csharp/language-reference/keywords/internal.md)
