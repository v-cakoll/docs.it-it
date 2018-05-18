---
title: Operatore -- (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 25f301bc0b2bc9bf51b0a44f26b2efabae00e452
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="---operator-c-reference"></a>Operatore -- (Riferimenti per C#)
L'operatore di decremento (`--`) decrementa il proprio operando di 1. L'operatore di decremento può apparire prima o dopo il proprio operando: `--variable` e `variable--`. Il primo esempio è un'operazione di decremento prefisso. Il risultato dell'operazione è il valore dell'operando "dopo" essere stato decrementato. Il secondo esempio è un'operazione di decremento suffisso. Il risultato dell'operazione è il valore dell'operando "prima" di essere decrementato.  
  
## <a name="remarks"></a>Note  
 I tipi numerico e di enumerazione hanno operatori di decremento predefiniti.  
  
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `--` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)). Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
