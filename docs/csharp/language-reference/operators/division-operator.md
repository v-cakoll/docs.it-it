---
title: Operatore / (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9e12e5c472266ea75d3f572a2091bd0784ea5dcf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Operatore / (Riferimenti per C#)
L'operatore di divisione (`/`) divide il primo operando per il secondo operando. Tutti i tipi numerici hanno operatori di divisione predefiniti.  
  
## <a name="remarks"></a>Note  
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `/` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)). Un overload dell'operatore `/` ha come risultato l'overload implicito dell'[operatore / =](division-assignment-operator.md).  
  
 Quando si dividono due numeri interi, il risultato è sempre un numero intero. Ad esempio, il risultato di 7/3 è 2. Per determinare il resto di 7/3, usare l'operatore di resto ([%](../../../csharp/language-reference/operators/modulus-operator.md)). Per ottenere un quoziente come numero razionale o come frazione, assegnare al dividendo o al divisore il tipo `float` o il tipo `double`. È possibile assegnare il tipo in modo implicito se si esprime il dividendo o il divisore come numero decimale mettendo una cifra sul lato destro del punto decimale, come mostra l'esempio seguente.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
