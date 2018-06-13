---
title: Operatore / (Riferimenti per C#)
ms.date: 04/04/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: 9d0bbff1fd9f4ab3c93c879d12ccd5fde1187b44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272571"
---
# <a name="-operator-c-reference"></a>Operatore / (Riferimenti per C#)
L'operatore di divisione (`/`) divide il primo operando per il secondo operando. Tutti i tipi numerici hanno operatori di divisione predefiniti.
  
## <a name="remarks"></a>Note  
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `/` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)). Un overload dell'operatore `/` ha come risultato l'overload implicito dell'[operatore / =](division-assignment-operator.md).  
  
 Quando si dividono due numeri interi, il risultato è sempre un numero intero. Ad esempio, il risultato di 7/3 è 2. Questo comportamento non deve essere confuso con la divisione con arrotondamento all'intero più grande (floor), perché l'operatore `/` arrotonda per difetto: -7/3 è -2.  
  
 Per ottenere un quoziente sotto forma di numero razionale, usare i tipi `float`, `double` o `decimal`. Esistono molti modi per eseguire conversioni tra i [tipi numerici predefiniti](../../../csharp/language-reference/keywords/reference-tables-for-types.md).  
  
 Per determinare il resto, usare l'[operatore di resto](../../../csharp/language-reference/operators/remainder-operator.md) `%`.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
