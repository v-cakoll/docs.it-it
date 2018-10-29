---
title: Operatore | (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 999df9db0819a5f33e21a29b892de0a8854dd5d8
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028177"
---
# <a name="-operator-c-reference"></a>Operatore | (Riferimenti per C#)
Gli operatori `|` binari sono predefiniti per i tipi integrali e `bool`. Per i tipi integrali, `|` calcola l'operatore OR bit per bit dei relativi operandi. Per gli operandi `bool`, `|` calcola l'operatore OR logico dei relativi operandi, ovvero, il risultato è `false` se e solo se entrambi gli operandi sono `false`.  
  
## <a name="remarks"></a>Note  
 L'operatore binario `|` valuta i due operatori indipendentemente dal valore del primo, diversamente dall'[operatore OR condizionale](conditional-or-operator.md) `||`.
 
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `|` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Operatori C#](../../../csharp/language-reference/operators/index.md)
