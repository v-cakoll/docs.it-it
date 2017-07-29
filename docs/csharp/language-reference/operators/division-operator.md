---
title: Operatore / (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
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
ms.openlocfilehash: 2972261996467f987fa457213b1bcb482d9f1519
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Operatore / (Riferimenti per C#)
L'operatore di divisione (`/`) divide il primo operando per il secondo operando. Tutti i tipi numerici hanno operatori di divisione predefiniti.  
  
## <a name="remarks"></a>Note  
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `/` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)). Un overload dell'operatore `/` ha come risultato l'overload implicito dell'[operatore / =](division-assignment-operator.md).  
  
 Quando si dividono due numeri interi, il risultato è sempre un numero intero. Ad esempio, il risultato di 7/3 è 2. Per determinare il resto di 7/3, usare l'operatore di resto ([%](../../../csharp/language-reference/operators/modulus-operator.md)). Per ottenere un quoziente come numero razionale o come frazione, assegnare al dividendo o al divisore il tipo `float` o il tipo `double`. È possibile assegnare il tipo in modo implicito se si esprime il dividendo o il divisore come numero decimale mettendo una cifra sul lato destro del punto decimale, come mostra l'esempio seguente.  
  
## <a name="example"></a>Esempio  
 [!code-cs[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Operatori C#](../../../csharp/language-reference/operators/index.md)

