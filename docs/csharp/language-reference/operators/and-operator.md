---
title: Operatore &amp; (Riferimenti per C#)
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f26305bfa1e8c9ba45493ad2ab4937d554590911
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="amp-operator-c-reference"></a>Operatore &amp; (Riferimenti per C#)
L'operatore `&` ha la funzione di operatore unario o binario.  
  
## <a name="remarks"></a>Note  
 L'operatore unario `&` restituisce l'indirizzo del relativo operando (richiede il contesto [unsafe](../../../csharp/language-reference/keywords/unsafe.md)).  
  
 Gli operatori `&` binari sono predefiniti per i tipi integrali e `bool`. Per i tipi integrali, & calcola l'operatore AND logico bit per bit dei relativi operandi. Per gli operandi `bool`, & calcola l'operatore AND logico dei relativi operandi, ovvero, il risultato è `true` se e solo se entrambi gli operandi sono `true`.  
  
 L'operatore binario `&` valuta entrambi gli operatori indipendentemente dal valore dal primo, diversamente dall'[operatore AND condizionale](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&`. Ad esempio:  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `&` (vedere [operator](../../../csharp/language-reference/keywords/operator.md)). Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione. Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
