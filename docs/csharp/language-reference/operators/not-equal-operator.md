---
title: Operatore != (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
ms.openlocfilehash: e409e2a80886fd5f7f4cdbeaa9b4e3325f8a967b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
