---
title: Operatore -- (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4eb68143103d44defeac7191e7c4ce7d1ee90e9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
