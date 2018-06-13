---
title: Operatore ~ (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 25b157fafde7d2b75cd8b112848a01e9b3fb0db2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270303"
---
# <a name="-operator-c-reference"></a>Operatore ~ (Riferimenti per C#)
L'operatore `~` esegue un'operazione di complemento bit per bit sul relativo operando, che ha l'effetto di invertire ogni bit. Gli operatori di complemento bit per bit sono predefiniti per [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) e [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
> [!NOTE]
>  È possibile anche usare il simbolo `~` per dichiarare i finalizzatori. Per altre informazioni, vedere [Finalizzatori](../../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
## <a name="remarks"></a>Note  
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `~`. Per altre informazioni, vedere l'argomento relativo all'[operatore](../../../csharp/language-reference/keywords/operator.md). Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)  
 [Finalizzatori](../../../csharp/programming-guide/classes-and-structs/destructors.md)
