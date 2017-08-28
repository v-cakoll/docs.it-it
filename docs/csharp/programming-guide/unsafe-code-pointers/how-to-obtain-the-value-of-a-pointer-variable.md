---
title: 'Procedura: ottenere il valore di una variabile puntatore (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
caps.latest.revision: 17
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
ms.openlocfilehash: 4cff42de07f2edb279ddd1cafefe9f4b67a38ce1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a>Procedura: ottenere il valore di una variabile puntatore (Guida per programmatori C#)
L'operatore di riferimento indiretto a puntatore consente di ottenere la variabile nella posizione indicata da un puntatore. L'espressione ha il seguente formato, dove `p` è un tipo di puntatore:  
  
```  
*p;  
```  
  
 Non è possibile usare l'operatore di riferimento indiretto unario o un'espressione di qualsiasi altro tipo diverso dal tipo puntatore. Non è inoltre possibile applicarlo a un puntatore [void](../../../csharp/language-reference/keywords/void.md).  
  
 Quando si applica l'operatore di riferimento indiretto a un puntatore [Null](../../../csharp/language-reference/keywords/null.md), il risultato dipende dall'implementazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente si accede a una variabile di tipo `char` usando puntatori di tipi diversi. Si noti che l'indirizzo di `theChar` varia da un'esecuzione all'altra, perché l'indirizzo fisico allocato a una variabile può cambiare.  
  
 [!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
 **Valore di theChar = Z**   
**Indirizzo di theChar = 12F718**  
**Valore di pChar = Z**   
**Valore di pInt = 90**    
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Espressioni puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Tipi di puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Tipi](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)

