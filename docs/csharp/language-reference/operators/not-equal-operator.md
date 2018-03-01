---
title: Operatore != (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b69d0b12734e690f0ba0209ccbbc7627ff92fe8a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Operatore != (Riferimenti per C#)
L'operatore di disuguaglianza (`!=`) restituisce false se gli operandi sono uguali, in caso contrario true. Gli operatori di disuguaglianza sono predefiniti per tutti i tipi, inclusi string e object. I tipi definiti dall'utente possono eseguire l'overload dell'operatore `!=`.  
  
## <a name="remarks"></a>Note  
 Per i tipi valore predefiniti, l'operatore di disuguaglianza (`!=`) restituisce true se i valori degli operandi sono diversi, in caso contrario false. Per i tipi riferimento diversi da `string`, `!=` restituisce true se i due operandi fanno riferimento a oggetti diversi. Per il tipo `string`, `!=` confronta i valori delle stringhe.  
  
 I tipi valore definiti dall'utente possono eseguire l'overload dell'operatore `!=` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)). Lo stesso vale per i tipi riferimento definiti dall'utente, anche se per impostazione predefinita `!=` si comporta come descritto in precedenza per entrambi i tipi riferimento predefiniti e definiti dall'utente. Se `!=` è sottoposto a overload, deve esserlo anche [==](../../../csharp/language-reference/operators/equality-comparison-operator.md). Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
