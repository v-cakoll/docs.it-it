---
title: Operatore ~ (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ~_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ffbfc379b7c021ccd8fbed9b796aa9fda6618b55
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Operatore ~ (Riferimenti per C#)
L'operatore `~` esegue un'operazione di complemento bit per bit sul relativo operando, che ha l'effetto di invertire ogni bit. Gli operatori di complemento bit per bit sono predefiniti per [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) e [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
> [!NOTE]
>  È possibile anche usare il simbolo `~` per dichiarare i finalizzatori. Per altre informazioni, vedere [Finalizzatori](../../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
## <a name="remarks"></a>Note  
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `~`. Per altre informazioni, vedere l'argomento relativo all'[operatore](../../../csharp/language-reference/keywords/operator.md). Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.  
  
## <a name="example"></a>Esempio  
 [!code-cs[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Operatori C#](../../../csharp/language-reference/operators/index.md)   
 [Finalizzatori](../../../csharp/programming-guide/classes-and-structs/destructors.md)

