---
title: Operatore *= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: e47bc5c681c94ac3fc5c345c56b3814350ffa5ec
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932350"
---
# <a name="-operator-c-reference"></a>Operatore *= (Riferimenti per C#)
Operatore di assegnazione di moltiplicazione binario.  
  
## <a name="remarks"></a>Note  
 Un'espressione che usa l'operatore di assegnazione `*=`, ad esempio  
  
```csharp  
x *= y  
```  
  
 equivale a  
  
```csharp  
x = x * y  
```  
  
 con la differenza che `x` viene valutato una sola volta. Per i tipi numerici, l'[operatore *](../../../csharp/language-reference/operators/multiplication-operator.md) è predefinito per l'esecuzione di moltiplicazioni.  
  
 L'operatore `*=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore *](../../../csharp/language-reference/operators/multiplication-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Operatori C#](../../../csharp/language-reference/operators/index.md)
