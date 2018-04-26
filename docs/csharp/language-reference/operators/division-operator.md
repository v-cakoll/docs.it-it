---
title: Operatore / (Riferimenti per C#)
ms.date: 04/04/2018
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
ms.openlocfilehash: 5b17d122e3e3f75012e084903b6f8975fb53d46c
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
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
